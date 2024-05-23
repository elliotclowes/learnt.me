---
id: 7860ec69-2924-4c35-a883-eb73bfe9f154
site_name: eugeneyan.com
author: Eugene Yan
date_published: 2022-08-14
date_saved: 2024-05-06
date_read: 2024-05-15
date_archived: 2024-05-15T06:59:46.000Z
original_url: https://eugeneyan.com/writing/simplicity/
omnivore_url: https://omnivore.app/me/simplicity-is-an-advantage-but-sadly-complexity-sells-better-18f4cfac43f
---

 - Site: eugeneyan.com
 - By: Eugene Yan
 - Date published: 2022-08-14
 - Date read: [[2024-05-15]]
 - [Read Original](https://eugeneyan.com/writing/simplicity/)
 - [Read on Omnivore](https://omnivore.app/me/simplicity-is-an-advantage-but-sadly-complexity-sells-better-18f4cfac43f)
 - Tags:  #Business_Analysis  #Technology 
 - Notes: 

**Note:** Below is the text from the article, with any ==highlights== done by me. None of the writing below is by me.

# Article text
\[[machinelearning](https://eugeneyan.com/tag/machinelearning/) [engineering](https://eugeneyan.com/tag/engineering/) [production](https://eugeneyan.com/tag/production/) [🔥](https://eugeneyan.com/tag/%F0%9F%94%A5/)\] · 7 min read 

We sometimes hear of a paper submission being rejected because the method was too simple, or a promotion being denied because the work artifacts lacked complexity. I think this can be partly explained by Dijkstra’s quote:

> “Simplicity is a great virtue but it requires hard work to achieve it and education to appreciate it. And to make matters worse: complexity sells better.” — [Edsger Dijkstra](https://en.wikipedia.org/wiki/Edsger%5FW.%5FDijkstra)

## Why does complexity sell better?[](#why-does-complexity-sell-better)

**Complexity signals effort.** Papers with difficult ideas and technical details suggest blood, sweat, and tears. Systems with more components and features hint at more effort than systems with less. Because complex artifacts are viewed as requiring more effort, they’re also deemed as more challenging to create and thus more worthy. And because of the perceived effort involved, they’re often judged to be higher quality.

**Complexity signals mastery.** A complex system with many moving parts suggests that the designer has proficiency over each part and the ability to integrate them. Inaccessible papers peppered with jargon and proofs demonstrate expertise on the subject. (This is also why we quiz interview candidates on algorithms and data structures that are rarely used at work.) If laymen have a hard time understanding the complex idea or system, its creator must be an expert, right?

**Complexity signals innovation.** Papers that invent entirely new model architectures are recognized as more novel relative to papers that adapt existing networks. Systems with components built from scratch are considered more inventive than systems that reuse existing parts. Work that _just_ builds on or reuses existing work isn’t _that_ innovative.

> “The idea is too simple, almost like a trick. It only changes one thing and everything else is the same as prior work.” — Reviewer 2

**Complexity signals more features.** Systems with components that can be mixed and matched suggest flexibility to cover all the bases. For example, supporting both SQL and NoSQL data stores, or enabling both batch and streaming pipelines. Because complex systems have more lego blocks relative to simple systems, they’re considered more adaptable and better able to respond to change.

All in all, the above leads to [complexity bias](https://fs.blog/complexity-bias/) where we give undue credit to and favour complex ideas and systems over simpler ones.

## Why is simplicity an advantage?[](#why-is-simplicity-an-advantage)

**Simple ideas and features are easier to understand and use.** This makes them more likely to gain adoption and create impact. They’re also easier to communicate and get feedback on. In contrast, complex systems are harder to explain and manage, making it difficult for users to figure out what to do and how to do it. Because there are too many knobs, mistakes are more frequent. Because there are too many steps, inefficiency occurs.

**Simple systems are easier to build and scale.** Systems that require less rather than more components are easier to implement. Using standard, off-the-shelf technology also makes it easier to find qualified people who can implement and maintain it. And because simpler systems have less complexity, code, and intra-system interactions, they’re easier to understand and test. In contrast, needlessly complex systems require more time and resources to build, leading to inefficiency and waste.

> When Instagram was acquired in 2012, it had a 13-person team serving tens of millions of users. It [scaled](https://www.scribd.com/document/89025069/Mike-Krieger-Instagram-at-the-Airbnb-tech-talk-on-Scaling-Instagram) and kept operational burden per engineer low by [sticking to proven technologies](https://instagram-engineering.com/what-powers-instagram-hundreds-of-instances-dozens-of-technologies-adf2e22da2ad) instead of new, shiny ones. When other startups adopted trendy NoSQL data stores and struggled, Instagram kept it lean with battle-proven and easy-to-understand PostgreSQL and Redis.

**Simple systems have lower operational costs.** ==Deploying a system is not the finish line; it’s the starting line. The bulk of the effort comes== _==after==_ ==the system is in production, likely by== _==someone other than the original team==_ ==that built it. By keeping systems simple, we lower their maintenance cost and increase their longevity.==

Simple systems have fewer moving parts that can break, making them more reliable and easier to fix. It’s also easier to upgrade or swap out individual components because there are fewer interactions within the system. In contrast, complex systems are more fragile and costly to maintain because there are so many components that need to be grokked by a limited team. Having more interdependent parts also makes troubleshooting harder.

> “The more simple any thing is, the less liable it is to be disordered, and the easier repaired when disordered.” — Thomas Paine, [Common Sense, 1776](https://en.wikipedia.org/wiki/Common%5FSense)

**Specific to machine learning, simple techniques don’t necessarily perform worse than more sophisticated ones.** A non-exhaustive list of examples include:

* [Tree-based models > deep neural networks](https://arxiv.org/abs/2207.08815) on 45 mid-sized tabular datasets
* [Greedy algorithms > graph neural networks](https://arxiv.org/abs/2206.13211) on combinatorial graph problems
* [Simple averaging ≥ complex optimizers](https://arxiv.org/abs/2201.04122) on multi-task learning problems
* [Simple methods > complex methods](https://www.sciencedirect.com/science/article/abs/pii/S014829631500140X) in forecasting accuracy across 32 papers
* [Dot product > neural collaborative filtering](https://dl.acm.org/doi/10.1145/3383313.3412488) in item recommendation and retrieval

![The simple dot product outperforms deep learning methods for recommendations.](https://proxy-prod.omnivore-image-cache.app/0x0,sq672i8O-sXZX_uzNpyIPnBHfYIpH4vVQNRcYJ1uJGI4/https://eugeneyan.com/assets/dot-product-vs-mlp.jpg "The simple dot product outperforms deep learning methods for recommendations.")

The humble dot product outperforms deep learning methods for recommendations ([source](https://dl.acm.org/doi/10.1145/3383313.3412488))

## What’s wrong with rewarding complexity?[](#whats-wrong-with-rewarding-complexity)

**It incentivizes people to make things unnecessarily complicated.** Using simple methods or building simple systems may appear easier and is thus valued less. As a result, people game the system to get more rewards and the simplest solution is no longer the most obvious one. Complexity begets more complexity, eventually making it impossible to work.

**It also encourages the “not invented here” mindset** where people prefer to build from scratch and shun reusing existing components even though it saves time and effort. This wastes time and resources and often leads to poorer outcomes.

Unfortunately, most promotion processes overemphasize complexity in work artifacts.

Ditto for machine learning paper submissions.

(If your idea didn’t get the credit it deserves, take comfort in the fact that [breakthroughs](https://twitter.com/rasbt/status/1548321060201803776) such as Kalman Filters, PageRank, SVM, LSTM, Word2Vec, Dropout, etc got rejected too. We’re generally bad at assessing how useful or impactful an innovation will be. 🤷)

## How should we think about complexity instead?[](#how-should-we-think-about-complexity-instead)

**==The objective should be to solve== _==complex==_ ==problems with as== _==simple==_ ==a solution as possible.==** Instead of focusing on the complexity of the _solution_, we should focus on the complexity of the _problem_. A simple solution demonstrates deep insight into the problem and the ability to avoid more convoluted and costly solutions. Often, the best solution is the simple one.

> “Everything should be made as simple as possible, but not simpler” — Albert Einstein

**Instead of having a complex, catch-all solution, consider multiple focused solutions.** A one-size-fits-all solution is usually less flexible and reusable than expected. And because it serves multiple use cases and stakeholders, it tends to be “tightly coupled” and require more coordination during planning and migrations. In contrast, it’s easier to operate—and unavoidably, deprecate—single-purpose systems.

## Is the juice worth the squeeze?[](#is-the-juice-worth-the-squeeze)

One way to overcome the complexity bias is [Occam’s razor](https://en.wikipedia.org/wiki/Occam's%5Frazor). It states that the simplest solution or explanation is usually the right one. Thus, let’s not be too quick to dismiss simple ideas or add unnecessary complexity to justify their worth.

Alternatively, ask yourself: Given the cost of complexity, is the juice worth the squeeze?

**Thanks** to Yang Xinyi and [Swyx](https://twitter.com/swyx) for reading drafts of this.

If you found this useful, please cite this write-up as:

> Yan, Ziyou. (Aug 2022). Simplicity is An Advantage but Sadly Complexity Sells Better. eugeneyan.com. https://eugeneyan.com/writing/simplicity/.

or

```dust
@article{yan2022simplicity,
  title   = {Simplicity is An Advantage but Sadly Complexity Sells Better},
  author  = {Yan, Ziyou},
  journal = {eugeneyan.com},
  year    = {2022},
  month   = {Aug},
  url     = {https://eugeneyan.com/writing/simplicity/}
}
```

Share on: 

Browse related tags: \[[machinelearning](https://eugeneyan.com/tag/machinelearning/) [engineering](https://eugeneyan.com/tag/engineering/) [production](https://eugeneyan.com/tag/production/) [🔥](https://eugeneyan.com/tag/%F0%9F%94%A5/)\] 

[Search](https://eugeneyan.com/search/ "Search") 

---

Join **6,700+** readers getting updates on machine learning, RecSys, LLMs, and engineering.

---