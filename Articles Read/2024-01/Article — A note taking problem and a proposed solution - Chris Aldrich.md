---
id: e2012924-43a4-4dd2-9fbe-10b65e63fe45
---

 - By: Chris Aldrich
 - Date published: 2020-08-29
 - Date saved: 2024-01-08
 - Date read: [[2024-01-08]]
 - [Read Original](https://boffosocko.com/2020/08/29/a-note-taking-problem-and-a-proposed-solution/)
 - [Read on Omnivore](https://omnivore.app/me/a-note-taking-problem-and-a-proposed-solution-chris-aldrich-18cea48a258)
 - Tags:  [[PIM]]
 - Notes: 

# Article Text

tl;dr 

It’s too painful to quickly get frequent notes into note taking and related platforms. Hypothes.is has an open API and a great UI that can be leveraged to simplify note taking processes.  

## Note taking tools

I’ve been keeping notes in systems like OneNote and Evernote for ages, but for my [memory-related research and work](https://boffosocko.com/category/memory/) in combination with my commonplace book for the last year, I’ve been alternately using TiddlyWiki (with TiddlyBlink) and WordPress (it’s way more than a blog.)

I’ve also dabbled significantly enough with related systems like Roam Research, Obsidian, Org mode/Org Roam, MediaWiki, DocuWiki, and many others to know what I’m looking for.

Many of these, particularly those that can be used alternately as commonplace books and [zettelkasten](https://en.wikipedia.org/wiki/Zettelkasten) appeal to me greatly when they include the idea of backlinks. (I’ve been using [Webmention](https://indieweb.org/Webmention) to leverage that functionality in WordPress settings, and MediaWiki gives it grudgingly with the “what links to this page” basic functionality that can be leveraged into better transclusion if necessary.)

## The major problem with most note taking tools

The final remaining problem I’ve found with almost all of these platforms is being able to quickly and easily get data into them so that I can work with or manipulate it. For me the worst part of note taking is the actual _taking_ of notes. Once I’ve got them, I can do some generally useful things with them—it’s literally the physical method of getting data from a web page, book, or other platform into the actual digital notebook that is the most painful, mindless, and useless thing for me.

### Evernote and OneNote

Older note taking services like Evernote and OneNote come with browser bookmarklets or mobile share functionality that make taking notes and extracting data from web sources simple and straightforward. Then once the data is in your notebook you can actually do some work with it. Sadly neither of these services has the backlinking functionality that I find has become _de rigueur_ for my note taking or knowledge wrangling needs.

### WordPress

My WordPress solutions are pretty well set since that workflow is entirely web-based and because WordPress has both bookmarklet and [Micropub](https://indieweb.org/Micropub) support. There I’m primarily using a [variety of feeds and services to format data into a usable form that I can use to ping my Micropub endpoint](https://boffosocko.com/2020/01/21/using-ifttt-to-syndicate-pesos-content-from-social-services-to-wordpress-using-micropub/). The [Micropub plugin](https://wordpress.org/plugins/micropub/) handles the post and most of the meta data I care about.

It would be great if other web services had support for Micropub this way too, as I could see some massive benefits to MediaWiki, Roam Research, and TiddlyWiki if they had this sort of support. The idea of Micropub has such great potential for great user interfaces. I could also see many of these services modifying projects like [Omnibear](https://omnibear.com/) to extend themselves to create highlighting (quoting) and annotating functionality with a browser extension.

With this said, I’m finding that **the user interface piece that I’m missing for almost all of these note taking tools is raw data collection**.

I’m not the sort of person whose learning style (or memory) is benefited by writing or typing out notes into my notebooks. I’d far rather just have it magically happen. Even copying and pasting data from a web browser into my digital notebook is a painful and annoying process, especially when you’re reading and collecting/curating as many notes as I tend to. I’d rather be able to highlight, type some thoughts and have it appear in my notebook. This would prevent the flow of my reading, thinking, and short annotations from being subverted by the note collection process.

## Different modalities for content consumption and note taking 

Based on my general experience there are only a handful of different spaces where I’m typically making notes.

### Reading online

A large portion of my reading these days is done in online settings. From newspapers, magazines, journal articles and more, I’m usually reading them online and taking notes from them there.

### .pdf texts

Some texts I want to read (often books and journal articles) only live in .pdf form. While reading them in an app-specific setting has previously been my preference, I’ve taken to reading them from within browsers. I’ll explain why in just a moment, but it has to do with a tool that treats this method the same as the general online modality. I’ll note that most of the .pdf specific apps have dreadful data export—if any.

### Reading e-books (Kindle, e-readers, etc.)

If it’s not online or in .pdf format, I’m usually reading books within a Kindle or other e-reading device. These are usually fairly easy to add highlights, annotations, and notes to. While there are some paid apps that can extract these notes, I don’t find it too difficult to find the raw file and cut and paste the data into my notebook of choice. Once there, going through my notes, reformatting them (if necessary), tagging them and expanding on them is not only relatively straightforward, but it also serves as a simple method for doing a first pass of spaced repetition and review for better long term recall.

### Lectures

Naturally taking notes from live lectures, audiobooks, and other spoken events occurs, but more often in these cases, I’m typically able to type them directly into my notebook of preference or I’m using something like my digital Livescribe pen for notes which get converted by OCR and are easy enough to convert in bulk into a digital notebook. I won’t belabor this part further, though if others have quick methods, I’d love to hear them.

### Physical books

While I love a physical book 10x more than the next 100 people, I’ve been trying to stay away from them because I find that though they’re easy to highlight, underline, and annotate the margins, it takes too much time and effort (generally useless for memory purposes for me) to transfer these notes into a digital notebook setting. And after all, it’s the time saving piece I’m after here, so my preference is to read in some digital format if at all possible.

## A potential solution for most of these modalities

For several years now, I’ve been enamored of the online [Hypothes.is](https://web.hypothes.is/) annotation tool. It’s open source, allows me reasonable access to my data from the (free) hosted version, and has a simple, beautiful, and fast process for bookmarking, highlighting, and annotating online texts on desktop and mobile. It works exceptionally well for both web pages and when reading .pdf texts within a browser window.

I’ve used it daily to make several thousand annotations on 800+ online web pages and documents. I’m not sure how I managed without it before. It’s the note taking tool I wished I’d always had. It’s a fun and welcome part of my daily life. It does exactly what I want it to and generally stays out of the way otherwise. I love it and recommend it unreservedly. It’s helped me to think more deeply and interact more directly with countless texts.

When reading on desktop or mobile platforms, it’s very simple to tap a browser extension and have all their functionality immediately available. I can quickly highlight a section of a text and their UI pops open to allow me to annotate, tag it, and publish. I feel like it’s even faster than posting something to Twitter. It is fantastically elegant.

The one problem I have with it is that while it’s great for collecting and aggregating my note data into my Hypothes.is account, there’s not much I can do with it once it’s there. It’s missing the notebook functionality some of these other services provide. I wish I could plug all my annotation and highlight content into spaced repetition systems or move it around and modify it within a notebook where it might be more interactive and cross linked for the long term. Sadly I don’t think that any of this sort of functionality is on Hypothes.is’ roadmap any time soon.

There is some great news however! Hypothes.is is [open source](https://github.com/hypothesis) and has a reasonable API. This portends some exciting things! This means that any of these wiki, zettelkasten, note taking, or spaced repetition services could leverage the UI for collecting data and pipe it into their interfaces for direct use.

As an example, what if I could quickly tell [Obsidian](https://obsidian.md/) to import all my pre-existing and future Hypothes.is data directly into my Obsidian vault for manipulating as notes? (And wouldn’t you know, the small atomic notes I get by highlighting and annotating are just the sort that one would like in a zettelkasten!) What if I could pick and choose specific course-related data from my reading and note taking in Hypothes.is (perhaps by tag or group) for import into [Anki](https://apps.ankiweb.net/) to quickly create some flash cards for spaced repetition review? For me, this combination would be my dream application!

These small pieces, loosely joined can provide some awesome opportunities for knowledge workers, students, researchers, and others. The education focused direction that Hypothes.is, many of these note taking platforms, and spaced repetition systems are all facing positions them to make a super-product that we all want and need.

### An experiment

So today, as a somewhat limited experiment, I played around with my [Hypothes.is atom feed](https://web.hypothes.is/help/atom-rss-feeds-for-annotations/) (<https://hypothes.is/stream.atom?user=chrisaldrich>, because [you know you want to subscribe to this](https://boffosocko.com/2019/11/07/following-people-on-hypothesis/)) and piped it into [IFTTT](https://ifttt.com/). Each post creates a new document in a OneDrive file which I can convert to a markdown .md file that can be picked up by my Obsidian client. While I can’t easily get the tags the way I’d like (because they’re not included in the feed) and the formatting is incredibly close, but not quite there, the result is actually quite nice.

Since I can “drop” all my new notes into a particular folder, I can easily process them all at a later date/time if necessary. In fact, I find that the fact that I might want to revisit all my notes to do quick tweaks or adding links or additional thoughts provides the added benefit of a first round of spaced repetition for the notes I took.

Some notes may end up being deleted or reshuffled, but one thing is clear: I’ve never been able to so simply highlight, annotate, and take notes on documents online and get them into my notebook so quickly. And when I want to do something with them, there they are, already sitting in my notebook for manipulation, cross-linking, spaced repetition, and review.

So if the developers of any of these platforms are paying attention, I (and I’m sure others) really can’t wait for plugin integrations using the full power of the Hypothes.is API that allow us to all leverage Hypothes.is’ user interface to make our workflows seamlessly simple.

### Chris Aldrich

 I'm a biomedical and electrical engineer with interests in information theory, complexity, evolution, genetics, signal processing, IndieWeb, theoretical mathematics, and big history. I'm also a talent manager-producer-publisher in the entertainment industry with expertise in representation, distribution, finance, production, content delivery, and new media. [ View all posts by Chris Aldrich ](https://boffosocko.com/author/chrisaldrich/) 