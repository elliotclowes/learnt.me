---
id: f1293cd0-d21d-4ba6-9df5-0898258374ce
site_name: matthewcornell.org
date_saved: 2024-07-16
date_read: 2024-07-21
date_archived: 2024-07-21T08:34:37.000Z
original_url: http://www.matthewcornell.org/blog/2005/8/21/my-big-arse-text-file-a-poor-mans-wikiblogpim.html
omnivore_url: https://omnivore.app/me/my-big-arse-text-file-a-poor-man-s-wiki-blog-pim-the-experiment--190b909f348
---

 - Site: matthewcornell.org
 - By: 
 - Date published: 
 - Date read: [[2024-07-21]]
 - [Read Original](http://www.matthewcornell.org/blog/2005/8/21/my-big-arse-text-file-a-poor-mans-wikiblogpim.html)
 - [Read on Omnivore](https://omnivore.app/me/my-big-arse-text-file-a-poor-man-s-wiki-blog-pim-the-experiment--190b909f348)
 - Tags:  #Plain_text  #Technology 
 - Notes: 

**Note:** Below is the text from the article, with any ==highlights== done by me. None of the writing below is by me.

# Article text
Sunday

## [My Big-Arse Text File - a Poor Man's Wiki+Blog+PIM](http://www.matthewcornell.org/blog/2005/8/21/my-big-arse-text-file-a-poor-mans-wikiblogpim.html) 

 Sunday, August 21, 2005 at 11:32AM 

 I was excited to to read [this article](http://www.oreillynet.com/pub/wlg/7567) (found via the unparalleled [43 Folders](http://www.43folders.com/2005/08/life%5Finside%5Fone.html)) describing one user's experiment with using a single (eventually large) text file to organize his [stuff](http://www.google.com/url?sa=t&ct=res&cd=3&url=http%3A//www.amazon.com/exec/obidos/tg/detail/-/0142000280%3Fv%3Dglance&ei=rEEGQ5vpK6bI-QHmwe3LDg). For me the reason it's an interesting read is that I've been using a plain text file for my professional log/diary/journal/notes since _Thu Sep 28 10:57:09 EDT 2000_. In this post I'd like to talk about how I use the file, in hopes that it will give me some motivation and ideas.

FYI, my current file (see description next) has \~14,000 lines (\~0.5MB), and my previous non-wiki file had \~55,000 lines (\~1.5MB).

**History**

I've been using a single file for my professional [ProgrammersNotebook](http://c2.com/cgi/wiki?ProgrammersNotebook) since at least 1997\. Initially it was a MS Word file (back in my Windows days), but when I moved to Linux I switched over to a simple [ASCII](http://en.wikipedia.org/wiki/ASCII) [file](http://www.chris.com/ascii/), which I edit in [Emacs](http://www.gnu.org/software/emacs/emacs.html). The reason I used word was for its outliner - I organized the file by making each day a level 1 entry, and I listed them in reverse chronological order so that I could start at the top when adding the latest entry. The outliner let me structure the file a bit by breaking multi-line activities into separate entities. (Hey - sounds like the GTD principle of making something a project if it requires more than one next action. I'm in trouble - everything has GTD overtones these days...)

I organized the first ASCII file using Emacs' [Outline](http://www.gnu.org/software/emacs/manual/html%5Fnode/Outline-Mode.html) [Mode](http://www.emacswiki.org/cgi-bin/wiki/OutlineMode), but organized just like the Word file - reverse chronological, with structure via nesting. Incremental search allowed me to find (but sometimes painfully) items I needed, such as [shell script](http://www.gnu.org/software/bash/bash.html) notes, [code](http://java.sun.com/) snippets, and what I had been spending my time on. The problem was that it didn't allow linking and tagging, one of the primary ways I use in structuring information.

So on 2004-07-19 I moved to a second format (still ASCII edited via Emacs), which I described in my post on [Photo Blogs, Wikis, and Memories for Life](http://www.matthewcornell.org/blog/2005/04/photo-blogs-wikis-and-memories-for.html). Briefly, the file has simple entries separated by '----' and a time-stamp at the end. For example:

  
  ----  
  talked w/PersonOne re: Google-style undergraduate programming  
  contest. not clear what the topic should be. also talked about future  
  fun projects. one possibility: ProxIncrVisualization  
  (2005-08-19 12:37:48)  
  ----  
  continued moving information over to planner. ugh- the undated pages  
  are a pain! wrote PersonTwo re: help, or maybe ordering a dated  
  set. PaperPlanners  
  (2005-08-19 08:32:37)  
  ----  
  MUS: http://www.sourcewatch.org/index.php?title=SourceWatch  
  CitizenshipOversightProject  
  (2005-08-19 08:29:25)  
  ----  
  ...  
  ----

The big improvement is linking and tagging via [WikiCase](http://c2.com/cgi/wiki?WikiCase) (AKA [CamelCase](http://c2.com/cgi/wiki?CamelCase) or WikiWords). This helps me navigate and find needed information. Of course it opens up another issue, that of consistent [tagging](http://en.wikipedia.org/wiki/Tags). But we'll save that for later. The only other formatting I use in the file is a) I _define_ an entry by placing a WikiWord on the first line by itself, and b) I have some shortcuts for words. The shortcuts are special two- or three-letter words that end with a colon (':') and start a line. My current ones include **IN** (inbox), **MUS** (Might Be Useful), **IDEA**, **COOL**, and **OFF** (vacation leave). Finally, URLs are treated specially - I don't mark them up, I just paste them verbatim.

Together these merge (in a very low cost way) some of the good ideas from Wikis, Blogs, and PIM tools, with the simplicity of a text file. (There's a nice discussion of them [here](http://www.ourpla.net/john/wikiweblogpim.html).)

**Emacs customization**

Well, not much really. All I have are keystrokes that create a new time-stamped entry and grab a URL's title. In addition I use the usual Emacs features like 'occur', interactive highlighting, and especially [hippie-expand](http://learn.tsinghua.edu.cn/homepage/2001315450/emacs24/emacs092.htm). I'd like to do more, but I just haven't had time.

**Isn't this just a cheap RDBMS?**

At first glance, yes, it's a just a text-based list of free-form records, which could be stored in a Relational Database System. (Actually, I helped build a new kind of database ([Proximity](http://kdl.cs.umass.edu/proximity/)) that directly supports representing semi-structured information like this, but that's another story.) My main reasons for not using a database are:

* Easy to set up.
* Customizable editors already available (easy to view, merge, format, search, edit, etc.)
* Easy to backup.
* Easy to write simple external tools to analyze, view, etc.
* Supports schema changes.

**Analysis and future**

All I'll say here is that I use the file in a few basic ways. (See [The Design and Long-Term Use of a Personal Electronic Notebook: A Reflective Analysis](http://www.visi.com/~snowfall/notebook.html) \- AKA A Personal Electronic Notebook, by Thomas Erickson - for a great analysis of a personal journal tool the author built then used.) Mostly I use it to capture ideas, notes, URLs, and work activity like tasks, coding, and email. I've made myself enter **every single URL** that I come across that I think might even remotely be useful, because many times I've had to spend a LONG TIME trying to find something I've seen before. (Related: [Stuff I've Seen](http://research.microsoft.com/adapt/sis/) and [Keeping Found Things Found](http://kftf.ischool.washington.edu/).)

To do nicer navigation and browsing I wrote a simple Java program (I used [Jetty](http://jetty.mortbay.org/jetty/)) to load the file's entries into RAM, show them chronologically, allow search, and turn WikiWords and URLs into links. I've used it a bit, but haven't been motivated to do more.

I think there's a great idea for a _Journal Construction Kit_ that supports the emergence of customized specialization (see [Jot](http://www.jot.com/) for a commercial effort in this area). Here's a question: Is a general tool to support this kind of activity possible? Maybe it would be similar to Jetbrain's [Meta Programming System](http://www.jetbrains.com/mps/start%5Fmps.html), but for information. Related: [Chandler](http://wiki.osafoundation.org/bin/view/Journal/IntroToChandlerTakeTwo), and [these](http://www.martinfowler.com/articles/languageWorkbench.html) [two](http://www.martinfowler.com/articles/mpsAgree.html) articles by Martin Fowler.

I'd love to hear from others who have created customized journal tools that support these features. I'm not excited by Emacs programming, I'm just trying to get work done. Any thoughts would be appreciated!