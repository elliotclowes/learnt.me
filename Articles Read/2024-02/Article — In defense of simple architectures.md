---
id: a6e9891b-16c6-4ab6-8b67-7c55a26a7f32
site_name: danluu.com
date_saved: 2024-02-20
date_read: 2024-02-21
date_archived: 2024-02-21T08:00:23.000Z
original_url: https://danluu.com/simple-architectures/
omnivore_url: https://omnivore.app/me/in-defense-of-simple-architectures-18dc726cf38
---

 - Site: danluu.com
 - By: 
 - Date published: 
 - Date read: [[2024-02-21]]
 - [Read Original](https://danluu.com/simple-architectures/)
 - [Read on Omnivore](https://omnivore.app/me/in-defense-of-simple-architectures-18dc726cf38)
 - Tags:  #Technology 
 - Notes: 

**Note:** Below is the text from the article, with any ==highlights== done by me. None of the writing below is by me.

# Article text
Wave is a $1.7B company with 70 engineers[1](#fn:R) whose product is a CRUD app that adds and subtracts numbers. In keeping with this, our architecture is a standard CRUD app architecture, a Python monolith on top of Postgres. [Starting with a simple architecture and solving problems in simple ways](https://twitter.com/danluu/status/1462607028585525249) where possible has allowed us to scale to this size while engineers mostly focus on work that delivers value to users.

Stackoverflow scaled up a monolith to good effect ([2013 architecture](https://nickcraver.com/blog/2013/11/22/what-it-takes-to-run-stack-overflow/) / [2016 architecture](https://nickcraver.com/blog/2016/02/17/stack-overflow-the-architecture-2016-edition/)), eventually getting acquired for $1.8B. If we look at traffic instead of market cap, Stackoverflow is among the top 100 highest traffic sites on the internet (for many other examples of valuable companies that were built on top of monoliths, [see the replies to this Twitter thread](https://twitter.com/danluu/status/1498678300163588096). We don’t have a lot of web traffic because we’re a mobile app, but Alexa still puts our website in the top 75k even though our website is basically just a way for people to find the app and most people don’t even find the app through our website).

There are some kinds of applications that have demands that would make a simple monolith on top of a boring database a non-starter but, for most kinds of applications, even at top-100 site levels of traffic, computers are fast enough that high-traffic apps can be served with simple architectures, which can generally be created more cheaply and easily than complex architectures.

Despite the unreasonable effectiveness of simple architectures, most press goes to complex architectures. For example, at a recent generalist tech conference, there were six talks on how to build or deal with side effects of complex, microservice-based, architectures and zero on how one might build out a simple monolith. There were more talks on quantum computing (one) than talks on monoliths (zero). Larger conferences are similar; a recent enterprise-oriented conference in SF had a double-digit number of talks on dealing with the complexity of a sophisticated architecture and zero on how to build a simple monolith. Something that was striking to me the last time I attended that conference is how many attendees who worked at enterprises with low-scale applications that could’ve been built with simple architectures had copied the latest and greatest sophisticated techniques that are popular on the conference circuit and HN.

Our architecture is so simple I’m not even going to bother with an architectural diagram. Instead, I’ll discuss a few boring things we do that help us keep things boring.

We’re currently using boring, synchronous, Python, which means that our server processes block while waiting for I/O, like network requests. We previously tried Eventlet, an async framework that would, in theory, let us get more efficiency out of Python, but ran into so many bugs that we decided the CPU and latency cost of waiting for events wasn’t worth the operational pain we had to take on to deal with Eventlet issues. The are other [well-known async frameworks for Python](https://twitter.com/mcfunley/status/1194713713330122752), but users of those at scale often also report [significant fallout from using those frameworks at scale](https://twitter.com/mcfunley/status/1194715290841432064). Using synchronous Python is expensive, in the sense that we pay for CPU that does nothing but wait during network requests, but since we’re only handling billions of requests a month (for now), the cost of this is low even when using a slow language, like Python, and paying retail public cloud prices. The cost of our engineering team completely dominates the cost of the systems we operate[2](#fn:B).

Rather than take on the complexity of making our monolith async we farm out long-running tasks (that we don’t want responses to block on) to a queue.

A place where we can’t be as boring as we’d like is with our on-prem datacenters. When we were operating solely in Senegal and Côte d'Ivoire, we operated fully in the cloud, but as we expand into Uganda (and more countries in the future), we’re having to split our backend and deploy on-prem to comply with local data residency laws and regulations. That's not exactly a simple operation, but as anyone who's done the same thing with a complex service-oriented architecture knows, this operation is much simpler than it would've been if we had a complex service-oriented architecture.

Another area is with software we’ve had to build (instead of buy). When we started out, we strongly preferred buying software over building it because a team of only a few engineers can’t afford the time cost of building everything. That was the right choice at the time even though [the “buy” option generally gives you tools that don’t work](https://danluu.com/nothing-works/). In cases where vendors can’t be convinced to fix showstopping bugs that are critical blockers for us, [it does make sense to build more of our own tools and maintain in-house expertise in more areas](https://danluu.com/in-house/), in contradiction to the standard advice that a company should only choose to “build” in its core competency. Much of that complexity is complexity that we don’t want to take on, but in some product categories, even after fairly extensive research we haven’t found any vendor that seems likely to provide a product that works for us. To be fair to our vendors, the problem they’d need to solve to deliver a working solution to us is much more complex than the problem we need to solve since our vendors are taking on the complexity of solving a problem for every customer, whereas we only need to solve the problem for one customer, ourselves.

A mistake we made in the first few months of operation that has some cost today was not carefully delimiting the boundaries of database transactions. In Wave’s codebase, the SQLAlchemy database session is a request-global variable; it implicitly begins a new database transaction any time a DB object’s attribute is accessed, and any function in Wave’s codebase can call commit on the session, causing it to commit all pending updates. This makes it difficult to control the time at which database updates occur, which increases our rate of subtle data-integrity bugs, as well as making it harder to lean on the database to build things like [idempotency keys](https://brandur.org/idempotency-keys) or a [transactionally-staged job drain](https://brandur.org/job-drain). It also increases our risk of accidentally holding open long-running database transactions, which can [make schema migrations operationally difficult](https://gocardless.com/blog/zero-downtime-postgres-migrations-the-hard-parts/).

Some choices that we’re unsure about (in that these are things we’re either thinking about changing, or would recommend to other teams starting from scratch to consider a different approach) were using RabbitMQ (for our purposes, Redis would probably work equally well as a task queue and just using Redis would reduce operational burden), using Celery (which is overcomplicated for our use case and has been implicated in several outages e.g. due to backwards compatibility issues during version upgrades), using SQLAlchemy (which makes it hard for developers to understand what database queries their code is going to emit, leading to various situations that are hard to debug and involve unnecessary operational pain, especially related to the above point about database transaction boundaries), and using Python (which was the right initial choice because of our founding CTO’s technical background, but its concurrency support, performance, and extensive dynamism make us question whether it’s the right choice for a large-scale backend codebase). None of these was a major mistake, and for some (e.g. Python) the downsides are minimal enough that it’s cheaper for us to continue to pay the increased maintenance burden than to invest in migrating to something theoretically better, but if we were starting a similar codebase from scratch today we’d think hard about whether they were the right choice.

Some areas where we’re happy with our choices even though they may not sound like the simplest feasible solution is with our API, where we use GraphQL, with our transport protocols, where we had a custom protocol for a while, and our host management, where we use Kubernetes. For our transport protocols, we used to use a custom protocol that runs on top of UDP, with an SMS and USSD fallback, [for the performance reasons described in this talk](https://www.youtube.com/watch?v=EAxnA9L5rS8). With the rollout of HTTP/3, we’ve been able to replace our custom protocol with HTTP/3 and we generally only need USSD for events like the recent internet shutdowns in Mali.

As for using GraphQL, we believe the pros outweigh the cons for us:

Pros:

* Self-documentation of exact return type
* Code generation of exact return type leads to safer clients
* GraphiQL interactive explorer is a productivity win
* Our various apps (user app, support app, Wave agent app, etc.) can mostly share one API, reducing complexity
* Composable query language allows clients to fetch exactly the data they need in a single packet roundtrip without needing to build a large number of special-purpose endpoints
* Eliminates bikeshedding over what counts as a RESTful API

Cons:

* GraphQL libraries weren’t great when we adopted GraphQL (the base Python library was a port of the Javascript one so not Pythonic, Graphene required a lot of boilerplate, and Apollo-Android produced very poorly optimized code)
* Default GQL encoding is redundant and we care a lot about limiting size because many of our customers have low bandwidth

As for Kubernetes, we use Kubernetes because knew that, if the business was successful (which it has been) and we kept expanding, we’d eventually expand to countries that require us to operate our services in country. The exact regulations vary by country, but we’re already expanding into one major African market that requires we operate our “primary datacenter” in the country and there are others with regulations that, e.g., require us to be able to fail over to a datacenter in the country.

An area where there’s unavoidable complexity for us is with telecom integrations. In theory, we would use a SaaS SMS provider for everything, but [the major SaaS SMS provider doesn’t operate everywhere in Africa](https://youtu.be/6tb8ALAvodM?t=196) and the cost of using them everywhere would be prohibitive[3](#fn:C). The earlier comment on how the compensation cost of engineers dominates the cost of our systems wouldn’t be true if we used a SaaS SMS provider for all of our SMS needs; the team that provides telecom integrations pays for itself many times over.

By keeping our application architecture as simple as possible, we can spend our complexity (and headcount) budget in places where there’s complexity that it benefits our business to take on. Taking the idea of doing things as simply as possible unless there’s a strong reason to add complexity has allowed us to build a fairly large business with not all that many engineers despite running an African finance business, which is generally believed to be a tough business to get into, which we’ll discuss in a future post (one of our earliest and most helpful advisers, who gave us advice that was critical in Wave’s success, initially suggested that Wave was a bad business idea and the founders should pick another one because he foresaw so many potential difficulties).

_Thanks to Ben Kuhn, Sierra Rotimi-Williams, June Seif, Kamal Marhubi, Ruthie Byers, Lincoln Quirk, Calum Ball, John Hergenroeder, Bill Mill, Sophia Wisdom, and Finbarr Timbers for comments/corrections/discussion._

---

1. If you want to compute a ratio, we had closer to 40 engineers when we last fundraised and were valued at $1.7B. [\[return\]](#fnref:R)
2. There are business models for which this wouldn't be true, e.g., if we were an ad-supported social media company, the level of traffic we'd need to support our company as it grows would be large enough that we'd incur a significant financial cost if we didn't [spend a significant fraction of our engineering time on optimization and cost reduction work](https://danluu.com/sounds-easy/). But, as a company that charges real money for a significant fraction of interactions with an app, our computational load per unit of revenue is very low compared to a social media company and it's likely that this will be a minor concern for us until we're well over an order of magnitude larger than we are now; it's not even clear that this would be a major concern if we were two orders of magnitude larger, although it would definitely be a concern at three orders of magnitude growth. [\[return\]](#fnref:B)
