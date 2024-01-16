---
id: 5ee9bf12-ed8b-45da-8c48-6c6b4b2c46cd
site_name: karl-voit.at
author: Karl Voit
date_published: 2014-05-14
date_saved: 2024-01-09
date_read: 2024-01-15
date_archived: 2024-01-15T17:29:28.000Z
original_url: https://karl-voit.at/managing-digital-photographs/
omnivore_url: https://omnivore.app/me/managing-digital-files-e-g-photographs-in-files-and-folders-18ced91620b
---

 - Site: karl-voit.at
 - By: Karl Voit
 - Date published: 2014-05-14
 - Date read: [[2024-01-15]]
 - [Read Original](https://karl-voit.at/managing-digital-photographs/)
 - [Read on Omnivore](https://omnivore.app/me/managing-digital-files-e-g-photographs-in-files-and-folders-18ced91620b)
 - Tags:  #PIM  #Technology 
 - Notes: 

**Note:** Below is the text from the article, with any ==highlights== done by me. None of the writing below is by me.

# Article text
* Updates:  
   * 2015-03-16: filtering photographs according to their GPS coordinates  
   * 2016-08-29: replaced outdated `show-sel.sh` method with new `filetags --filter` method  
   * 2017-08-28: Email comment on geeqie video thumbnails  
   * 2018-03-06: Links to the concept by Julian Kahnert  
   * 2018-05-06: Linked video of [a 45 minute talk I gave](https://glt18-programm.linuxtage.at/events/321.html) at [Linuxtage Graz 2018](https://glt18.linuxtage.at/)  
   * 2018-07-22: moved folder hierarchy explanation to [an article on its own](https://karl-voit.at/folder-hierarchy)  
   * 2019-07-09: Email comment on genealogy and characters to avoid in file names  
   * 2020-06-06: Wrote a better intro. Removed detailed setup instructions and referred to [the latest archive page](https://web.archive.org/web/20200602015020/https://karl-voit.at/managing-digital-photographs/) or the README files of the tools mentioned instead.  
   * 2020-06-17: [The Linux Magazine](https://www.linux-magazine.com/) features [my file-management article](https://www.linux-magazine.com/Issues/2020/236/Semantic-File-Organization) in [its July 2020 issue](https://www.linux-magazine.com/Issues/2020/236). My article is even the main headline on [the title page](https://www.linux-magazine.com/Issues/2020/236);-)  
   * 2020-10-25: Email Comment by Peter Bamm on Emacs integration

Managing digital files is mostly done in an ad hoc way. People are collecting files on their computers and using folder hierarchies that grow organically. This does not scale well when it comes to retrieval success. Looking for a specific file is a task that often does not result in finding the information or it requires some level of frustration.

I'm somebody who has spent many years with personal organization schemes. I tried all kinds of tools and methods. I changed my personal file management concept multiple times in order to minimize file curation effort, maximize consistency and retrieval success. For a couple of years, I was a professional researcher for this topic, [writing a PhD thesis on a new file management method](https://karl-voit.at/tagstore/en/papers.shtml) that [tries to overcome the limitations of the desktop metaphor of our desktops](https://karl-voit.at/2018/08/25/deskop-metaphor). Scientific results from peers, my own findings and methods from this PhD project had a huge influence on the method I developed afterwards.

This article is explaining the concept I developed and which I am using on a daily basis. I'm using digital photographs as an use-case example. However, the method described is **not about image files only**.

My method consists of multiple ingredients:

1. My simple folder hierarchy.
2. A file name convention including tags.
3. A set of self-written tools that minimizes my personal effort as much as possible.
4. Advanced information retrieval features that you can't find anywhere else like TagTrees.

If you don't want to read this long article about my method now, you might find motivation to do so afterwards by ==taking a look at== ==[this online demo of some features of the tools involved](https://karl-voit.at/demo-filetags-intro)==. It doesn't explain my method at all but it should transport some aspects from a practical view. This might give you enough curiosity to come back here and read the rest on how to combine those features to an efficient method.

==Further more, here is== ==[a 45 minute talk I gave](https://glt18-programm.linuxtage.at/events/321.html)== ==at== ==[Linuxtage Graz 2018](https://glt18.linuxtage.at/)== presenting the workflows and tools mentioned in this article: ([alternative video hosted on media.CCC.de](https://media.ccc.de/v/GLT18%5F-%5F321%5F-%5Fen%5F-%5Fg%5Fap147%5F004%5F-%5F201804281550%5F-%5Fthe%5Fadvantages%5Fof%5Ffile%5Fname%5Fconventions%5Fand%5Ftagging%5F-%5Fkarl%5Fvoit))

You will find following sections below. Bold section names are not related to the example use-case of photographs only:

* My Requirements
* iPhoto, Picasa, … Considered Harmful
* **My File Name Convention**
* **My General Folder Structure**
* My Workflows  
   * Moving files from my SD card to the computer, rotating portrait images, and renaming files  
   * Folder navigation, viewing, renaming, deleting image files  
   * **Adding and removing tags**  
   * **Advanced file renaming with appendfilename**  
   * Play movie files  
   * Open in an external image editor  
   * **Move to archive folder**  
   * Rotate images (loss-less)  
   * Visualizing GPS coordinates  
   * Filtering photographs according to their GPS coordinates  
   * **Showing a sub-set of a given set**  
   * Summary with a real world example  
   * **Retrieving files (filter, TagTrees)**
* Finally
* Other Tools
* (Comments and Backlinks)

For the example use-case, the story goes like this: I am a passionate photographer when being on vacation or whenever I see something beautiful. This way, I collected many [JPEG](https://en.wikipedia.org/wiki/Jpeg) files over the past decades. Here, I describe how I manage my digital photographs while avoiding any [vendor lock-in](http://en.wikipedia.org/wiki/Vendor%5Flock-in) which binds me to a temporary solution and leads to loss of data in the long run. I prefer solutions where I am able to **invest my time and effort for a long-term relationship**.

Before I start explaining my method, we should come to an agreement whether or not we do have the same set of requirements I am trying to address with my method. If you are into [raw image formats](https://en.wikipedia.org/wiki/Raw%5Fimage%5Fformat), storing your photographs somewhere in the cloud or anything else very special to you (and not to me), you might not get satisfied with the things described here. At least for the photograph use-case. Decide yourself.

## My Requirements

For **getting the photographs (and movies) from my digital camera to my computer**, I just want to put the SD card into my computer and invoke the fetch-workflow. This thing also has to **pre-process the files** to meet my file name convention (described further down) and to rotate images that are in portrait orientation (and not in landscape).

Those image files are copied to my photograph inbox folder `$HOME/tmp/digicam/`. In this folder, I want to **look through my image files and play movies** to **sort out/delete, rename, add/remove tags, and put sets of related files into separate destination folders**.

After that, I want to **navigate through my set of folders** containing the sets of image/movie files. In rare occasions, I want to **open an image file in an independent image processing tool** like [the GIMP](http://www.gimp.org/). For **rotating JPEG files**, I want to have a quick method which does not require an image processing tool and which is rotating JPEG images [in a loss-less way](http://petapixel.com/2012/08/14/why-you-should-always-rotate-original-jpeg-photos-losslessly/).

My photographs contain [GPS](https://en.wikipedia.org/wiki/Gps) coordinates. Therefore, I need a method to **visualize GPS coordinates for single files as well as for a set of files** showing the path I was walking.

There is another nice feature I want to use: imagine a beautiful vacation in Venice where you took hundreds of photographs. Each of them is so beautiful so that you do not want to delete some of them. On the other side, you might want to get a much smaller set of photographs for presenting to your friends at home. And they are only expecting maybe two dozens of files before being too jealous. Therefore, I want to be able to **define and present a pre-defined sub-set of photos**.

In terms of being independent and **avoid lock-in effects**, I do not want to use a tool I am not able to use when a company discontinues a product or service. For the very same reason and because I am a privacy-aware person, **[I do not want to use any cloud-based service](https://karl-voit.at/cloud)**. In order to keep myself open for new possibilities, I do not want to invest any effort in something which is only available on one specific operating system platform. **Basic stuff has to be available on any platform** (viewing, navigation, ...). But the **full set of requirements have to work on my main system**, in my case Debian GNU/Linux running the [Xfce Desktop Environment](https://xfce.org/).

If you have read [my analysis of the built-in Windows 10 feature for tagging files](https://karl-voit.at/2019/11/26/Tagging-Files-With-Windows-10), you may recognize that OS-specific or file-system-specific tagging functionality is in direct conflict with many requirements mentioned above.

In summary and according to [my tool choice workflow](https://karl-voit.at/2021/01/18/tool-choices), my requirements are:

* must haves  
   * avoid lock-in situations  
   * off-cloud for privacy reasons  
   * (semi-)automatic process camera → computer  
   * automatic pre-processing images (rotation)  
   * look through a folder of images  
   * add and curate tags  
   * define and present a pre-defined sub-set of photos
* nice to haves  
   * use any independent image viewer tool  
   * visualize GPS coordinates from meta-data

Before I describe my current solutions to this fairly large set of requirements mentioned above, I have to explain my general folder structure and file naming convention I also use for digital photographs. But first, there is an important fact you have to consider:

## iPhoto, Picasa, ... Considered Harmful

Software tools which manage collections of photographs do provide pretty cool features. They offer a nice user interface and try to give you cozy work-flows for all kinds of requirements.

The issue I do have with them is multi-fold. They mostly use proprietary storage formats for settings, image files and image meta-data. This is a huge problem, when you are going to change to a different software in a couple of years. Trust me: **you are going to switch** some day in any case for different reasons.

If you are in the position where you need to switch to a different all-in-one tool, you are going to realize that iPhoto or Picasa do store original image files and everything you did to them separately. Rotation of images, adding description to image files, tags, cropping, and so forth: **everything will be lost forever** if you are not able to export it and re-import it to the new tool. Chances are very high that you are not going to do this without loss of information or data.

I do not want to invest any effort in a tool which locks away my work. **I refuse to lock-in myself to any proprietary tool.** Been there, done that. Learned my lessons.

If you follow [my recommended way of selecting tools](https://karl-voit.at/2021/01/18/tool-choices), you can minimize the risk of losing data or meta-data in the first place.

## My File Name Convention

Avoiding any lock-in effects is the main reason why I keep meta-data like time-stamps, image descriptions or tags in the file name itself. ==File names are permanent unless I manually change them. They do not get lost when I backup my photographs or when I copy them to USB thumb drives or onto another operating systems. Everybody and everything is able to read and process them. Even any future system is able to read and process them. It's the one common denominator that most likely will survive the next decades for sure.== 

As a result, a file name convention is necessary to be defined and followed so that even software tools are able to extract important meta-data from the file names properly.

All my files which do have a relation to a specific day or a point in time are prefixed with a **date-stamp** or a **time-stamp** according to an adopted [ISO 8601](https://en.wikipedia.org/wiki/Iso%5Fdate) format. I have to use adopted ISO time-stamp format because colons - that are part of the standard definition - are not allowed for files stored in the Windows [file system NTFS](https://en.wikipedia.org/wiki/Ntfs). Therefore, I replaced colons with dots for separating hours from minutes from the optional seconds.

Here is an example file name with a date-stamp:

Another example file name with a time-stamp including optional seconds:

 2014-05-09T22.19.58 Susan presenting her new shoes.jpg	  

In case of **time or date duration**, I separate the two date- or time-stamps with two dashes:

As with all meta-data within file names, time/date-stamps in file names have the advantage that they remain unchanged until I manually change them. Meta-data which is included in the file content itself (like [Exif](https://en.wikipedia.org/wiki/Exif)) tends to get lost when files are processed via tools that do not take care of those meta-data. Additionally, starting a file name with such a date/time-stamp ensures that files are displayed in file managers in temporal order instead of alphabetic order according to their descriptions. The alphabet is a [totally artificial sort order](http://www.isisinform.com/reinventing-knowledge-the-medieval-controversy-of-alphabetical-order/) and it is typically less practical for locating files by the user when compared to temporal order which seems to support the way that the human brain associates events.

When I want to assign **tags** to a file name, I place them between the original file name and the [file name extension](https://en.wikipedia.org/wiki/File%5Fname%5Fextension) separated by a space, two minus signs and an additional space: "` -- `". My tags are lower case English words which do not contain spaces or special characters. Sometimes, I might use concatenated words like `quantifiedself` or `usergenerated`. I [tend to prefer general categories](http://karl-voit.at/tagstore/en/papers.shtml) instead of more (too) more specific describing tags. I re-use my tags on Twitter [hashtags](https://en.wikipedia.org/wiki/Hashtag), file names, folder names, bookmarks, blog entries like this one, and so forth. Please do read [my general recommendations on using tags in an efficient way](https://karl-voit.at/2022/01/29/How-to-Use-Tags).

The example files from above with some tags assigned:

 2014-05-09 Budget export for project 42 -- finance company.csv
 2014-05-09T22.19.58 Susan presenting her new shoes -- family clothing.jpg
 2014-05-09--2014-05-13 Jazz festival Graz -- folder tourism music.pdf	  

==Tags as part of the file name have several advantages. You are able to locate files with the help of tags by using your usual desktop search engine. Tags in file-names can not be lost because of copying on different storage media. This== usually happens, whenever a system uses a different storage place than the file name: meta-data data-base, [dot-files](https://en.wikipedia.org/wiki/Dot-file), [alternate data streams](https://en.wikipedia.org/wiki/NTFS#Alternate%5Fdata%5Fstreams%5F.28ADS.29), and so forth.

Of course, please do **avoid special characters**, umlauts, colons, and so forth in file and folder names in general. Especially when you synchronize files between different operating system platforms. Meanwhile, I'm totally fine with spaces in file names. Those had negative impact in certain situations years ago. Nowadays, there is no need to replace spaces with underscores any more.

My **file name convention for folders** is the same as for files although I do not tag folders (yet).

==Note: Because of the clever== ==[filenametimestamps](https://github.com/novoid/Memacs/blob/master/docs/memacs%5Ffilenametimestamps.org)====-module of== ==[Memacs](https://github.com/novoid/Memacs)====, all files and folders with a date/time-stamp appear on the corresponding time/day on my== ==[Org mode](https://karl-voit.at/orgmode)== ==calendar (agenda). This way, I get a very cool overview on what happened on each day including all photographs I took. But this is a different story.== 

## My General Folder Structure

==In== ==[this blog article](https://karl-voit.at/folder-hierarchy)====, I describe my most important folders within my home folder. Please do read it now in order to know how I organize my archive folder structure. I'll wait for you to return.== 

Finished?

OK, then let's continue ...

## My Workflows

Tadaa, after you learned about my file name convention and my folder structure, here are my current workflows and tools I use for the requirements I described further up.

Please note that **you have to understand, what you are doing** when following my directions. My examples here contain folder paths and more things that **only works on my machine or my set-up**. **You have to adapt things** like paths, file names, and so forth to meet your situation.

### Workflow: Moving files from my SD card to the computer, rotating portrait images, and renaming files

When I want to move data from my digital camera to my GNU/Linux computer, I take out its Mini-SD storage card and put it in my computer. Then it gets mounted on `/media/digicam` automatically.

==Then, I invoke== ==[getdigicamdata.sh](https://github.com/novoid/getdigicamdata.sh)== ==which does several things: it moves the files from the SD card to a temporary folder for processing. The original file names are being converted to lower-case characters. All portrait photographs are rotated using== ==[jhead](http://www.sentex.net/%3Ccode%3Emwandel/jhead/)====. Also with jhead, I generate file-name time-stamps from the Exif header time-stamps. Using== ==[date2name](https://github.com/novoid/date2name)== ==I add time-stamps also to the movie files. After processing all those files, they get moved to the destination folder for new digicam files: $HOME/tmp/digicam/tmp/~.== 

Photographs from my Android phone are synchronized to my desktop computer using [Syncthing](https://syncthing.net/) automatically.

### Workflow: Folder navigation, viewing, renaming, deleting image files

For skimming through my image and movie files, I prefer to use [geeqie](http://geeqie.sourceforge.net/) on GNU/Linux. It is a fairly lightweight image browser which has one big advantage too many file browsers are missing: I can add external scripts/tools which can be invoked by a self-defined keyboard shortcut. This way, I am able to extend the feature-set of the image browser by arbitrary external commands I wrote myself.

Basic image management functionality is built-in to geeqie: navigating my folder hierarchy, viewing image files in window-mode and in full-screen more (shortcut `f`), renaming file names, deleting files, showing Exif meta-data (shortcut `Ctrl-e`).

### Workflow: Adding and removing tags

I created a Python script called [filetags](https://github.com/novoid/filetag) which I use for [adding and removing tags](https://karl-voit.at/demo-filetags-tagging) to single files as well as a set of files. Please visit [its project page](https://github.com/novoid/filetags/) for learning how to set up the tool and [integrate it to your favorite file or image browser](https://github.com/novoid/filetags/blob/master/Integration.org).

Tagging itself is not a straight-forward thing to do right from the start. [I would definitively read my recommendations on using tags in an efficient way](https://karl-voit.at/2022/01/29/How-to-Use-Tags).

In geeqie, you can add a keyboard shortcut in `Edit > Preferences > Keyboard`. I associated `t` with the `filetags` command. For removing tags, I created a keyboard shortcut for `T`.

When I skim though image files in the geeqie file browser, I select files I want to tag (one to many) and press `t`. Then, a small window pops up and asks me for one or more tags. After confirming with `Return`, these tags gets added to the file names.

The same goes for removing tags: selecting multiple files, pressing `T`, entering tags to be removed, and confirming with `Return`. That's it. There is [almost no simpler way to add or remove tags to files](http://karl-voit.at/tagstore/).

For digital photographs, I use tags like, e.g., `specialL` for landscape images that I consider suitable for desktop backgrounds and so forth, `specialP` for portrait photographs I would like to show to others, `sel` for a selection, and many more.

Please note that on 2020-06-06, I removed detailed setup instructions from this article. If you want to take a look on these instructions, you might want to visit [the last archive version of the old article that contains detailed geeqie integration instructions](https://tinyurl.com/y6z6t7sz). For all of my self-programmed tools, the GitHub project READMEs provide setup information.

### Workflow: Advanced file renaming with appendfilename

Renaming a large set of files can be a tedious process. With original file names like , the process to add a description to its file name is quite annoying. You are going to press `Ctrl-r` (rename) in geeqie which opens the file rename dialog. The base-name (file-name without the file extension) is marked by default. So if you do not want to delete/overwrite the file name (but append to it), you have to press the cursor key for `<right>`. Then, the cursor is placed between the base name and the extension. Type in your description (don't forget the initial space character) and confirm with `Return`.

Since I minimize manual effort, I set up a different solution for me.

With [appendfilename](https://github.com/novoid/appendfilename), [my process is simplified](https://karl-voit.at/demo-appendfilename) to gain maximum user experience for appending text to file names: When I press `a` (append) in geeqie, a dialog window pops up, asking for a text. After confirming with `Return`, the entered text gets placed between the time-stamp and the optional tags.

For example when I press `a` on and I type `Pick-nick in Graz`, the file name gets changed to `2014-04-20T17.09.11_p1100386 Pick-nick in Graz.jpg`. When I press `a` once again and enter `with Susan`, the file name gets changed to `2014-04-20T17.09.11_p1100386 Pick-nick in Graz with Susan.jpg`. When the file name got tags as well, the appended text gets appended before the tag-separator.

This way, I do not have to be afraid to overwrite time-stamps or tags. The process for renaming gets much more enjoyable for me.

And the best part: when I want to add the same text to multiple selected files, this also works with appendfilename.

### Workflow: Play movie files

On GNU/Linux, I use [mplayer](http://www.mplayerhq.hu/) to play-back video files. Since geeqie does not play movie files by itself, I set-up mplayer within geeqie such that I just have to press `o` when the geeqie cursor is highlighting the video file. That's it.

### Workflow: Open in an external image editor

I rarely want to be able to quickly edit image files in the GIMP. Therefore, I added a shortcut `g` and associated it with the external editor "GNU Image Manipulation Program" (GIMP) which was already created by default by geeqie.

This way, only pressing `g` opens the current image file in the GIMP.

### Workflow: Move to archive folder

Now that I have added comments to my file names, I want to move single files to `$HOME/archive/events_memories/2014/` or set of files to new folders within this folder like

 $HOME/archive/events_memories/2014/2014-05-08 Business-Marathon After-Show-Party	  

The usual way is to select one or multiple files and move them to a folder with the shortcut `Ctrl-m`.

So booooring.

Therefore, I (again) wrote a Python script which does this job for me: [move2archive](https://github.com/novoid/move2archive) (in short: `m2a`) expects one or more files as command line parameters. Then, a dialog appears where I am able to enter an optional folder name. When I do not enter anything at all but press `Return`, the files gets moved to the folder of the corresponding year. When I enter a folder name like `Business-Marathon After-Show-Party`, the date-stamp of the first image file is appended to the folder:

 $HOME/archive/events_memories/2014/2014-05-08 Business-Marathon After-Show-Party	  

The resulting folder gets created, and the files gets moved.

Once again: I am in geeqie, select one or more files, press `m` (move) and either press only `Return` (no special sub-folder) or enter a descriptive text which is the name of the sub-folder to be created (optionally without date-stamp).

**No image managing tool is as quick and as fun to use as my geeqie with appendfilename and move2archive via shotcuts.** 

### Workflow: Rotate images (loss-less)

Usually, portrait photographs are being marked automatically as portrait photographs by my digital camera. However, there are certain situations (like taking a photograph from above the motif) where my camera gets it wrong. In those **rare cases**, I have to manually fix the orientation.

==You have to know that the JPEG file format is a lossy format which should be used only for photographs and not for computer-generated stuff like screen-shots or diagrams. Rotating a JPEG image file in the dumb way usually results in decompressing/visualizing the image file, rotating the resulting image, and re-encoding the result once again. This causes a resulting image with== ==[much worse image quality than the original image](http://petapixel.com/2012/08/14/why-you-should-always-rotate-original-jpeg-photos-losslessly/)====.== 

Therefore, you should use a lossless method to rotate you JPEG image files. I integrated [exiftran](http://manpages.ubuntu.com/manpages/raring/man1/exiftran.1.html) to geeqie and created geeqie keyboard shortcuts for `[` (counter-clock-wise) and `]` (clock-wise).

### Workflow: Visualizing GPS coordinates

My digital camera has a GPS sensor which stores the current geographic location within the Exif meta-data of the JPEG files. The location data gets stored in [WGS 84](https://en.wikipedia.org/wiki/WGS84#A%5Fnew%5FWorld%5FGeodetic%5FSystem:%5FWGS%5F84) format like "47, 58, 26.73; 16, 23, 55.51" (latitude; longitude). This is not human-readable in the sense I would expect: either a map or a location name. Therefore, I added functionality to geeqie so, that I am able to see the location of a single image file on [OpenStreetMap](http://www.openstreetmap.org/): `Edit > Configure Plugins... > New` 

Mapped to the keyboard shortcut `G`, I can quickly get to the **map position of its location of a single image file**.

When I want to visualize the **positions of multiple JPEG image files as a path**, I am using [GpsPrune](http://activityworkshop.net/software/gpsprune/). I was not able to derive a method where GpsPrune takes a set of files as command line parameters. And because of this, I have to manually start GpsPrune, select a set of files or a folder with `File > Add photos`.

This way, I get a dot for each JPEG location on a map of OpenStreetMap (if configured so). By clicking on such a dot, I get details of the corresponding image.

If you happen to be abroad while taking photographs, visualizing the GPS positions is a **great help for adding descriptions** to the file name!

### Workflow: Filtering photographs according to their GPS coordinates

This is no workflow of mine. For the sake of completeness, I list features of tools that make this workflow possible. What I would like to do is looking for only those photographs out of a big pile of images, that are within a certain area (rectangle or point + distance).

So far, I found only [DigiKam](https://en.wikipedia.org/wiki/DigiKam) which is able to [filter according to a rectangle](https://docs.kde.org/trunk5/en/extragear-graphics/digikam/tool-geolocation.html#geolocation-search). If you know another tool, please add it to the comments below or write an email.

### Workflow: Showing a sub-set of a given set

As described in the requirements above, I want to be able to define a sub-set of files within a folder in order to present this small collection to other people.

The work-flow is pretty simple: I add a tag (via `t`/filetags) to the files of the selection. For this, I use the tag `sel` which is short for "selection". After I tagged the set of files, I can press `s` which I associated with a script that shows only the files tagged with `sel`.

Of course, this also works with any tag or tag combination. Therefore, with the same method, you are able to get a decent overview on all photos of your wedding that are tagged with "church" and "rings".

Nifty feature, isn't it? :-)

What `filetags` with parameter `--filter` does is basically the following: the user gets asked to enter one or more tags. Then, all matching files of the current folder are linked to `$HOME/.filetags_tagfilter/` using [symbolic links](https://en.wikipedia.org/wiki/Symbolic%5Flink). Then, a new geeqie instance is started which shows the linked files.

After quitting this new geeqie instance, you see the old geeqie instance, from where you invoked the selection process.

### Summary with a real world example

Wow, this was a very long blog entry. No wonder that you might have lost the overview here and there. To sum up the things I am able to do within geeqie (that extends the standard feature set), I have this cool table below:

| shortcut | function                         |
| -------- | -------------------------------- |
| m        | move2archive                     |
| o        | open (for non-images)            |
| a        | add text to file name            |
| t        | filetags (add)                   |
| T        | filetags (remove)                |
| s        | filetags (filter)                |
| g        | gimp                             |
| G        | show GPS position                |
| \[       | lossless rotate counterclockwise |
| \]       | lossless rotate clockwise        |
| Ctrl\-e  | EXIF                             |
| f        | full-screen                      |

Parts of a file name (including its path) and tools I use to manipulate the components accordingly:

 /this/is/a/folder/2014-04-20T17.09 Picknick in Graz -- food graz.jpg
 [ move2archive  ] [  date2name   ] [appendfilename] [ filetags ]	  

In practice, I do the following steps to get my photographs from the camera to my archive: I put the SD memory card into my SD card reader of my computer. Then I start [getdigicamdata.sh](https://github.com/novoid/getdigicamdata.sh). After it is finished, I open `$HOME/tmp/digicam/tmp/` within geeqie. I skim through the photographs and delete the ones that did not work out. If there is an image with the wrong orientation, I correct it by `[` or `]`.

In a second run, I add descriptions to files I consider worth commenting on (`a`). Whenever I want to add tags I do so as well: I quickly mark all files that should share a tag (`Ctrl` \+ mouse-click) and tag them using [filetags](https://github.com/novoid/filetag) (`t`).

To combine files from a given event, I select corresponding files and move them to their "event-folder" within the yearly archive folder by typing the event description in [move2archive](https://github.com/novoid/move2archive) (`m`). The rest (no special event folder) is moved to the yearly archive directly by move2archive (`m`) without stating a event description.

To finish my work-flow, I delete all files on my SD card, dismount it from the operating system, and put it back into my digital camera.

That's it.

Because this work-flow requires almost no overhead at all, commenting, tagging, and filing photographs is not a tedious job any more.

### Workflow: Retrieving files (filter, TagTrees)

Additional to the normal file navigation methods everybody is using already, I have contributed some tag-based retrieval methods as well.

My filetags tool is able to [filter according to tags](https://karl-voit.at/demo-filetags-filter) as already mentioned above. This way, I might retrieve files within a given folder sub-hierarchy by choosing one or more tags. The pop-up file browser shows then only files that do have all of the given tags assigned.

An even cooler method is using the **TagTrees** feature of filetags. Since this is a rather new idea, I have to explain it a bit further.

Consider following file:

 My new car -- car hardware expensive.jpg	  

Now you [generate the TagTrees](https://karl-voit.at/demo-filetags-mk-tagtrees) with the `--tagtrees` parameter of filetags. Then you'll find [links](https://en.wikipedia.org/wiki/Symbolic%5Flink) to this file within the sub-directories of the temporarily navigational hierarchy of `~/.filetags` which the default target directory:

* `~/.filetags/`  
   * `new/`  
         * `My new car -- car hardware expensive.jpg`(link)  
   * `hardware/`  
         * `My new car -- car hardware expensive.jpg`(link)  
   * `expensive/`  
         * `My new car -- car hardware expensive.jpg`(link)

So far, so simple. However, TagTrees are taking this concept even further. The very same file is also linked to `new/hardware/`, `new/expensive/`, `hardware/new/`, `expensive/new/hardware/` and all other combination of those three tags of the file. The folders that contain links for those three tags are:

* `~/.filetags/`  
   * `new/`  
         * `hardware/`  
                  * `expensive/`  
         * `expensive/`  
                  * `hardware/`  
   * `hardware/`  
         * `new/`  
                  * `expensive/`  
         * `expensive/`  
                  * `new/`  
   * `expensive/`  
         * `hardware/`  
                  * `new/`  
         * `new/`  
                  * `hardware/`

For example, within the folder `new/expensive/` you will find all files that have at least the tags "new" and "expensive" in any order. Having a TagTrees hierarchy in-front of you, you can really get the most of your filetags. This is a really cool way of accessing files by associations instead of remembering their location.

Files of the current directory that don't have any tag at all, are linked directly to `~/.filetags` so that you can find and tag them easily.

I personally, do use this feature within my image viewer of choice ([geeqie](http://geeqie.sourceforge.net/)). I mapped it to `Shift-T` because `Shift-t` is occupied by `filetags` for tagging purposes of course. So when I am within my image viewer and I press `Shift-T`, TagTrees of the currently shown images are created. Then an additional image viewer window opens up for me, showing the resulting TagTrees. This way, I can quickly navigate through the tag combinations to easily interactively filter according to tags.

Please note: when you are [tagging or using appendfilename on linked files within the TagTrees](https://karl-voit.at/demo-filetags-tag-tagtrees), only the current link(s) and the original file(s) get updated with the new name. All other links to this modified filename within the other directories of the TagTrees gets broken. You have to re-create the TagTrees to update all the links after modifying file names.

## Finally

So, this is a detailed description of my work-flows related to photographs and movies I make. You probably have found additional stuff I might be interested in. So please do not hesitate and leave a comment or email by using the links below.

I also would like to get feed-back if my work-flow works for you as well. And: if you have published your work-flows or find descriptions of other peoples work-flows, please do leave a comment as well!

Have fun and don't waste your time with the wrong tools or inefficient methods!

## Other Tools

Read about [gThumb in this article](https://karl-voit.at/2017/02/19/gthumb).

Please do suggest your tools of choice when you've got the feeling that they fit my requirements mentioned above.

## Email Comment Thomas

> Date: Sat, 26 Aug 2017 22:05:09 +0200  
> Hello Karl,  
> I like your articles and work with memacs and of course orgmode but I am not very familiar with python by the way... in your blog post of "managing-digital-photographs" you write about to open videos with[Geeqie](http://geeqie.sourceforge.net/).  
> It works, but I cant see any video thumbnails in the browser of Geeqie. Do you have any suggestions to get this to work?  
> Thank you, Thomas

Hi Thomas,

Thanks for your kind words. I always feel great when somebody finds my work useful in his/her life. Unfortunately most of the time, I never hear of them.

Yes, I sometimes use Geeqie to visualize folders that not only contain image files but movie files as well. In those cases, I don't see any thumbnail image of the video. You're absolutely right, there are many file browsers out there which are able to display some kind of preview image of a video.

Quite frankly, I never thought of video thumbnails and I don't miss them. A quick research in the preferences and with my search engine did not suggest that there is a possible way to enable video previews in Geeqie. So no luck here.

## Email Comment Julian Kahnert and Even More Advanced Tools

Julian Kahnert sent me an email where he thanked me for the ideas and the concept. [He took the concept](https://juliankahnert.de/2018-03-03-pdf-archiver/) and created a tool called [PDF-Archiver](https://github.com/JulianKahnert/PDF-Archiver). It's a macOS GUI app to rename and tag PDF files.

He is using a different file name convention: with "this is a document" as the description and "bill" and "vacation" as tags. The different separation characters `-` and `_` allow for searching more explicitely. For example, when you locate `_vacation` you are looking for the tag "vacation" and not the word "vacation" within the file description.

Although this is a very clever move, I personally do prefer spaces as separation characters because I still write many file names by hand, which is tedious with `-` and `_` as characters in-between.

I, too, analyse the content of PDF files to derive file names automatically. This is done via [guess-filename](https://github.com/novoid/guess-filename.py) which uses the old filename and the file contents to generate new filenames. I did not promote the tool that much because you need to personalize its code to meet your file names and your documents, of course. However, when guess-filename is set-up, renaming files to their proper and descriptive filename is really fast and fun.

In addition to [move2archive](https://github.com/novoid/move2archive), I also use a simple but very handy shell script named [guess-target-folder.sh](https://gist.github.com/novoid/c4a239abc4027ecfd14e9904da88e6a1) to guess a target folder that differs from my `$HOME/archive/events_memories/<YEAR>/` structure. For example, so far, I wanted to have all files related to certain companies, insurances, and so forth in one folder per company. To be honest with you, I can't explain why I started this in the first place. This could be solved via tags and the usual year-folders as well.

Nevertheless, [guess-target-folder.sh](https://gist.github.com/novoid/c4a239abc4027ecfd14e9904da88e6a1) is also a cool aid for moving around files that are not archived at all. When commuting, I do listen to the previous evening news which I download every morning. The downloaded files do get their proper file name via [guess-filename](https://github.com/novoid/guess-filename.py) and [guess-target-folder.sh](https://gist.github.com/novoid/c4a239abc4027ecfd14e9904da88e6a1) is moving them to [the synchronization folder](https://syncthing.net/) of my mobile. When I leave my house, my mobile has the latest news ready to be listened to while waiting for and riding the bus.

## Email Comment on Metadata

Somebody sent me an email comment and discussed the meta-data in filename approach of mine:

> Putting tags in file name will hit length limits.  
> I have been thinking about meta data and would like to recommend this:<https://git-annex.branchable.com/design/metadata/>(which might solve some backup problem as well) Metadata is not easy to get right, but at least this can be an interim solution.  
> What do you think?

While the danger of getting file name length issues is absolutely true in theory (especially with Windows), I did not get into any issue on GNU/Linux (mainly) and Windows 10 myself so far by using filetags.

My file names tend to look like:

 2018-06-05 Article about backup techniques from heise iX 6-2018 -- scan software exp2014.pdf	  

This is descriptive, has a few tags (I don't recommend to use more than let's say five per file) and is fine with file length borders.

Maybe you have a different tagging strategy?

[In this talk I was referring to tagging in general](https://media.ccc.de/v/GLT18%5F-%5F321%5F-%5Fen%5F-%5Fg%5Fap147%5F004%5F-%5F201804281550%5F-%5Fthe%5Fadvantages%5Fof%5Ffile%5Fname%5Fconventions%5Fand%5Ftagging%5F-%5Fkarl%5Fvoit) as well. Maybe this gives you an idea how I circumvent the file length issue?

Thanks for the link on git-annex.

I used - or better tested - git-annex myself.

There are lots of different approaches for the metadata problem as you already mentioned. OS X once had streams that were promising but proprietary and now dead (or implemented differently).

Technology-wise, there are many ideas that solve the issue in a clever way. My priority was to get a solution that lasts. Not a few years but my whole life. I don't want to tag thousands of files these days and have to migrate to a different metadata technique when switching to a different operating system in the future. Who knows how long git-annex is maintained? Maybe ten years? Or twenty? Or three? Nobody can tell and I don't want to ride a dead horse (or maintain unsupported code myself).

Forther more: my approach is compatible with **any** software there is. Every operating system, every backup tool, every synchronization solution. With git-annex-like metadata, OS X streams or any other metadata approach, I'd lose meta-data when doing backups, copying files to USB memory sticks and so forth.

I think you get the idea why I keep to file names for meta-data.

## Email Comment on Genealogy and Characters to Avoid in File Names

> I just want to say thanks for this post. Most people with serious family archives of photos will have to get across all of this. I will be attending to the detail in the post with some effort to work out how to fit it into my workflow.  
> I am coming from a genealogy/family tree research background background on pathway and filenaming issues, and have written a post on the cross OS issues in filenaming, and a little bit on diffeering file systems, with an eye to portability through time and across peoples machines, originally/mostly via sneakernets - via USB thumbdrives. the post can be seen as a bit of an addenda for you post in regards to avoiding special characters and such.  
> MetaSource\_DATE\_DataPoints for genealogy & other microhistory projects, a pathway, directory/folder and file naming system at my blog: <https://formeika.wordpress.com/2017/03/11/metasource%5Fdate%5Fdatapoints/>  
> I am glad other people are thinking about such things, particularly database lock-in, almost regardless of the proprietory lock-in. It might be different if the file systems were databases, and could be expect to be so into the future.  
> all the best[meika loofs samorzewski](http://meika.loofs-samorzewski.com/)

I am familiar with [reserved characters within file names](https://en.wikipedia.org/wiki/Filename#Reserved%5Fcharacters%5Fand%5Fwords) and had to [use a modified ISO format for time-stamps](https://karl-voit.at/managing-digital-photographs) with [filetags](https://github.com/novoid/filetags/) for this reason. However, it is a good idea to have a reminder at this place as well. Don't use: `/\?%*:|"<>` and avoid dots and spaces if you want to be sure for one hundred percent.

## Email Comment by Peter Bamm on Emacs integration

> Hello Karl,  
> Thank you for all your great work and input!  
> I have been using org-mode for a few months now and I am probably as enthusiastic about it as you are.  
> Somehow on my org-mode journey I stumbled upon your name and therefore came across your very nice presentations at the Grazer Linux Tage.  
> Your file structuring inspired me, especially the innovation of tag trees. I was just wondering: Is it possible to combine all this with org-mode? For example, with org-mode attachments or file links?  
> Wouldn't it be cool to handle all your files through org-mode attachments and somehow use the generated data directories from emacs/org-mode to handle all your files?  
> Thanks a lot for your time and keep on emacsing ;)

Hi Peter,

Thanks for the encouraging words. It means a lot to me.

Although I'm [a very intense user of Emacs Org mode](https://karl-voit.at/orgmode), I don't use much from this file management concept from within Emacs. Most of my file management happens in the shell, [zsh](https://en.wikipedia.org/wiki/Zsh) in my case [with grml's settings](https://grml.org/zsh/).

Occasionally, I'm using dired as an Emacs file manager. However, since it is really, really slow on my machines, I prefer the shell whenever possible.

Sometimes, I'm using [the Org attachment concept](https://orgmode.org/manual/Attachments.html). It's great but as long as I'm not using dired as my main file management tool, it has limited advantages to my workflows.

However, there are two things somebody might interpret as connection points between my file management method and Emacs I am using on a daily basis.

The first, is the use of my `tsfile:` links whenever I link to a file within my Emacs. This is even cooler than attachments because `tsfile:` links almost can't get broken even when I move files or rename them. The custom link is defined in [my setup](https://github.com/novoid/dot-emacs/blob/master/config.org) where you can get all the details by searching for "tsfile". For this method, you'll need something like [this Memacs module](https://github.com/novoid/Memacs/blob/master/docs/memacs%5Ffilenametimestamps.org) to derive the file index. At least that's how I'm doing it.

Secondly, the same principle is implemented in my blogging system called [lazyblorg](https://github.com/novoid/lazyblorg) for linking image files. You can read about this very nice thing on [this Wiki page](https://github.com/novoid/lazyblorg/wiki/Images).

Both things aren't directly related to TagTrees or filetags. They are advantages I get by sticking to my file name convention and using `date2name` for most files.

If you are looking for a direct Emacs connection, you can, for example, use [filetags.el](https://github.com/beutelma/filetags.el) instead of [filetags](https://github.com/novoid/filetags). And there is [date2name.el](https://github.com/DerBeutlin/date2name.el) instead of [date2name](https://github.com/novoid/date2name). I'm not using them myself but the guy who wrote them is very good.

## Backlinks

Here are some external sources that somehow link back to this page:

* 2018-04-28: [The Advantages of File Name Conventions and Tagging](https://glt18-programm.linuxtage.at/events/321.html) at Linuxdays Graz 2018  
   * [Video recording of the talk](https://media.ccc.de/v/GLT18%5F-%5F321%5F-%5Fen%5F-%5Fg%5Fap147%5F004%5F-%5F201804281550%5F-%5Fthe%5Fadvantages%5Fof%5Ffile%5Fname%5Fconventions%5Fand%5Ftagging%5F-%5Fkarl%5Fvoit)
* 2020-01: [LinuxUser 03.2020](https://www.linux-community.de/magazine/linuxuser/2020/03/): I wrote a German article on my method:  
   * [Semantisches Tagging erleichtert das Dateimanagement: Am Namen sollt Ihr sie erkennen](https://www.linux-community.de/ausgaben/linuxuser/2020/03/am-namen-sollt-ihr-sie-erkennen/)
* 2020-06: [Linux Magazine Issue 236 (July 2020)](https://www.linux-magazine.com/Issues/2020/236) features [an English translation of the German article above](https://www.linux-magazine.com/Issues/2020/236/Semantic-File-Organization). It's the main headline on the title page of the magazine.