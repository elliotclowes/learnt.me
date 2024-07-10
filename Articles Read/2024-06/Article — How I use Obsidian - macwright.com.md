---
id: f6839271-f51a-417e-a162-4a2402ccf758
site_name: macwright.com
author: Tom MacWright
date_published: 2024-06-16
date_saved: 2024-06-17
date_read: 2024-06-18
date_archived: 2024-06-18T16:27:14.000Z
original_url: https://macwright.com/2024/06/16/how-i-use-obsidian.html
omnivore_url: https://omnivore.app/me/https-macwright-com-2024-06-16-how-i-use-obsidian-html-19025116424
---

 - Site: macwright.com
 - By: Tom MacWright
 - Date published: 2024-06-16
 - Date read: [[2024-06-18]]
 - [Read Original](https://macwright.com/2024/06/16/how-i-use-obsidian.html)
 - [Read on Omnivore](https://omnivore.app/me/https-macwright-com-2024-06-16-how-i-use-obsidian-html-19025116424)
 - Tags:  #Obsidian  #Note_taking  #Technology 
 - Notes: 

**Note:** Below is the text from the article, with any ==highlights== done by me. None of the writing below is by me.

# Article text
I wrote a little bit about [how I published this microblog](https://macwright.com/2023/12/14/blog-about-blog) with [Obsidian](https://obsidian.md/), and I recently [published an Obsidian plugin](https://macwright.com/2024/06/02/freeform). I’m a fan: I’ve used a lot of note-taking systems, but the only ones that really stuck were [Notional Velocity](https://en.wikipedia.org/wiki/Notational%5FVelocity) and [The Archive](https://zettelkasten.de/the-archive/). And now, Obsidian.

## Before Obsidian

Versus Notational Velocity / The Archive:

* I miss the native mac experience of those apps. Obsidian’s performance is pretty great, but every once in a while I’ll notice some behavior that reminds me that it’s an embedded web view.
* Obsidian has pretty good momentum and I think the odds of it sticking around for the long term are good. Versus Notational Velocity, which stalled and was restarted twice by different development teams, and The Archive, which I think has a very small dev team.
* Obsidian also succeeds in a solid iPhone app. I don’t write notes on my iPhone, but I like having them accessible. You can technically make this work with The Archive, but it didn’t work very well.

Anyway, to my Obsidian setup. It’s not fancy, because I have never found a structured system that makes sense to me.

## Obsidian features that I don’t use

There are a lot of features that I don’t use:

* I don’t use the ‘graph view’ at all. It’s fun to look at it, but I’ve never found it, or any other graph view, useful, ever? I’ve [written about this before, how some of these ‘second brain’ representations seem like a fantasy](https://macwright.com/2022/01/10/semblance-of-understanding).
* I don’t use the [Canvas feature at all](https://obsidian.md/canvas). Mind mapping doesn’t work for me.
* I don’t use tags at all. I haven’t found anything that tags provide for me that I can’t get with search.
* Very rarely I’ll add an image to a note in Obsidian. I don’t use any other kinds of attachments. I use [DevonThink](https://www.devontechnologies.com/apps/devonthink) for PDFs and documents and it is incredible.

I’ve turned off the graph view and tab view using combinations of the [Hider](https://github.com/kepano/obsidian-hider) and [Minimal Theme settings](https://github.com/kepano/obsidian-minimal) plugins.

## Theme & aesthetic

![[CleanShot%202024-06-16%20at%2011.26.33%402x.png]]

This is what my Obsidian setup looks like right now, as I’m writing this. I followed a lot of advice in [Everyday Obsidian](https://www.everydayobsidian.com/) to get it there, so I don’t want to share everything that got me there, but anyway: it’s the Minimal theme, and the [iA Quattro](https://github.com/iaolo/iA-Fonts) font. Like I said, the graph view, canvas, and tags aren’t useful to me, so I hide them. I usually hide the right bar too. I’ve been trying out vertical tabs, and am on the fence as to whether I’ll keep them around.

The Minimal Theme is a godsend. Obsidian by default looks okay-ish - much better than [Roam Research](https://roamresearch.com/) or [LogSeq](https://github.com/logseq/logseq), but with the Minimal Theme it looks really nice, on par with some native apps.

## Organization

I use pretty rough folders with broad categories - notes on meetings, trips, finance, and so on. There are some limited subfolders, but I’m not trying to get that precise. It is impossible to mirror the brain’s structure in this kind of organization, and…

I think, importantly, that _simple organizational structures are good for thinking_. I see all of these companies pitching like hierarchical nested colored tags that are also folders and spatially arranged, and I think it’s essentially bad. Forcing notes into a simple set of folders is useful. Having to write linear text and choose what to prioritize is useful.

Think back to writing essays in high school: that forced us to produce structure from our thoughts. That is a good skill to have, it helps us think. It is strictly better than an English class in which all of the term papers are word clouds of vibes with arrows pointing everywhere.

## The day note

Every day I’m computering, I’ll create a day note in Obsidian and use it as the anchor for everything else I write or am working on. Basically there are three shortcuts I rely on all the time that I’ve customized:

* **Command-D**: Daily Notes: Open Today’s Daily Note
* **Command-0**: Templates: Insert Current Date
* **Command-. (Command-Period)**: Tasks: Toggle task done

The daily note template has nothing in it. I tried [inserting prev and next links into it](https://macwright.com/2024/05/14/previous-next-links-in-obsidian), but it was more annoying than helpful. I have the “Open Daily Note on Startup” option toggled on.

The daily note is usually a bulleted list with links to pages of what I’m working on or writing that day. The **Command-.** keybinding is wonderful, because it doesn’t just toggle a task to done or not - if you have plain text on a line, it will toggle between a list bullet, a new todo item, and a finished todo item. I use that keybinding all the time.

The other thing is **Command-0** for today’s date. This is something I learned from the [Zettelkasten](https://zettelkasten.de/) ideology: this is a lazy form of an [ID](https://zettelkasten.de/posts/add-identity/) for me. A lot of my ongoing notes will consist of multiple sections where I type `##` for a heading and then **Command-0** to insert the day’s date, to add updates. Automatic date management is extremely useful to me: I’ve always had a lot of trouble calculating, understanding, and remembering dates. Could probably diagnose or pathologize that, but let’s leave that for another day: thankfully calendars exist.

## Views & properties

I use [properties](https://help.obsidian.md/Editing+and+formatting/Properties) a lot. Even if they don’t help that much with ‘retrieval’ or aren’t useful in views, I just like the idea of regularized structures. So many notes have a `url` property for the URL of that technology, person, place, etc.

For some categories, like “stuff I own,” I use properties for the order number, color, price, and other trivia. Every once in a while this comes in handy when something needs a new battery and I can easily look up what kind it takes. I’m also constantly trying to [buy more durable things](https://www.reddit.com/r/BuyItForLife/), and it has been really useful to have a record of how long a pair of jeans last (not long!).

## Plugins

All together, I use:

* [Freeform](https://macwright.com/2024/06/02/freeform), of course, for data visualizations.
* [Auto link title](https://obsidian.md/plugins?id=obsidian-auto-link-title) for pasting links and getting decent titles. This is _mostly_ great, but the average quality of page titles on the internet is poor, because of SEO, and it also can’t handle private URLs.
* [Minimal Theme Settings](https://obsidian.md/plugins?id=obsidian-minimal-settings) for tweaking little theme settings.
* [Hider](https://obsidian.md/plugins?id=obsidian-hider) for tweaking even more theme settings.
* [Dataview](https://obsidian.md/plugins?id=dataview) for making automatic tables of notes for which I’ve added properties.
* [Tasks](https://obsidian.md/plugins?id=obsidian-tasks-plugin) for fancier todo lists. I am on the fence about this one and might not use it for much longer. I still use [Things](https://culturedcode.com/things/) for tasks, too, and it’s better in most ways.
