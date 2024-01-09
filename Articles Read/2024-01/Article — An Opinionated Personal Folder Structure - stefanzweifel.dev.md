---
id: 806dfb57-44ef-4ca0-9b30-04e80493cfc2
---

 - By: 
 - Date published: 2023-09-16
 - Date saved: 2024-01-08
 - Date read: [[2024-01-08]]
 - [Read Original](https://stefanzweifel.dev/posts/2023/09/16/an-opinionated-personal-folder-structure)
 - [Read on Omnivore](https://omnivore.app/me/an-opinionated-personal-folder-structure-stefanzweifel-dev-18cea272dd0)
 - Tags:  [[Johnny.Decimal]]  [[PIM]] 
 - Notes: 


# Article text
In an age where kids grow up with apps and search engines and don't know what URLs or files and folders are[1](#fn:1), it might come across as weird to read a post about a _personal folder structure_.

Everyone does it differently. Some put all those PDFs, receipts, images and documents they get on their desktop or in the "Downloads" folder on their computer. Others add them in a "Documents" folder on a cloud storage provider like Dropbox, Google Drive or Microsoft OneDrive.

Some put everything in a single folder. Others try to bring organisation to the chaos by adding a "personal", "finances" or "travel" folder.

In this post I would like to share my personal folder structure I use and have refined over the last 5 years.

## Johnny Decimal

I discovered the [Johnny Decimal](https://johnnydecimal.com/)\-system (JD) many years ago and fell in love with it. It gave me the constraints needed to bring order to my chaos.

==The basic rule of== _==JD==_ ==is to have up to 10== _==areas==_ ==and each area has up to 10== _==categories==_==. You're not== _==allowed==_ ==to create subfolders.==  
==If applied correctly, this means you have a folder structure that is at most two levels deep.== (I make a few exceptions for _year_\-folders as you will see in the example below)

These constraints helped me to move away from a single folder containing all the invoices from the last 10 years and away from a deeply nested folder structure for the old software I collect (Software → Windows → Productivity → Office → …).

I first applied _JD_ to my files and folders stored on my NAS in 2018 and wrote about it in [2020](https://stefanzweifel.dev/posts/2020/08/04/synology-nas-setup-2020#content-folder-structure--synology-drive).

Since then, a couple of things changed.  
In 2022 I revised the entire structure and consolidated **all** my files in iCloud Drive. I don't maintain a different structure on Google Drive or on my NAS. Everything is in iCloud Drive now.[2](#fn:2)

## My Current Folder Structure

It took a couple of weeks to find the right shape when I revised my folder structure in 2022.

In the years before, I noticed that I got sloppy and added folders where none should exists or stopped sorting files as I just didn't know where to put them.

Once agreed that I need to change something, I took pen and paper and wrote down different ideas of the areas and categories I needed.

I salvaged a couple of areas and from my existing NAS structure, but redefined all the categories. I simplified. Merged similar sounding categories with each other. Cut those that I barely ever used. Freed up _number spaces_.

Below is the entire folder structure as a tree on which I settled on and which I've been using since late 2022.

I've redacted some names and omited some private folders; but I think you get the gist. (I will explain some of the areas and categories at the end of this list. Scroll on if you're interested.)

```angelscript
├── 00-00 INBOX
├── 10-19 Personal-Documents
│ ├── 11 Personal
│ │ ├── 11.01 Identification
│ │ ├── 11.02 Correspondences (by year)
│ │ ├── 11.03 Civil Defense Schaffhausen
│ │ ├── 11.04 Civil Defense Zürich
│ │ ├── 11.05 <Car A>
│ │ ├── 11.06 Specialized Crux E5 Bike
│ │ └── 11.07 Emergency Plan
│ ├── 12 Health
│ │ ├── 12.01 Medical History
│ │ └── 12.02 Fitness Guides
│ ├── 13 Contracts
│ │ ├── 13.01 <Mobile Carrier>
│ │ ├── 13.02 <Car Sharing Provider>
│ │ └── 13.03 <Home Internet Provider>
│ ├── 14 Travels
│ │ ├── 14.01 Amsterdam 2024
│ │ ├── 14.02 Greece 2024
│ ├── 15 Insurances
│ │ ├── 15.01 Old-age and Survivors Insurance
│ │ ├── 15.02 <Insurer> Health Insurance
│ │ ├── 15.03 <Insurer> Home Insurance
│ │ ├── 15.04 <Insurer> Car Insurance
│ │ ├── 15.05 <Insurer> Travel Insurance
│ │ └── 15.06 Apple Care
│ └── 16 Housing
│     └── 16.01 <Current City>
│         ├── 16.01.01 Correspondence <Landlord>
│         │ ├── 2022
│         │ └── 2023
│         ├── 16.01.02 Energy Bills
│         │ ├── 2022
│         │ └── 2023
│         ├── 16.01.03 City Correspondence
│         └── 16.01.04 Rental deposit
├── 20-29 Finances
│ ├── 21 Banking & Investments
│ │ ├── 21.01 <Bank A> Cash Account
│ │ ├── 21.02 <Bank A> Savings Account
│ │ ├── 21.03 <Bank B> Savings Account
│ │ ├── 21.04 Pension Account
│ │ ├── 21.05 <Bank C> (Closed)
│ │ ├── 21.08 <Credit Card A>
│ │ ├── 21.09 <Investment Portfolio A>
│ │ ├── 21.10 Book Keeping
│ │ ├── 21.12 GitHub Sponsors
│ ├── 22 Donations (by Year)
│ │ ├── 2022
│ │ └── 2023
│ ├── 23 Taxes (by Year)
│ │ ├── 23.01 Zurich 2022
│ │ └── 23.02 Zurich 2023
│ └── 24 Purchases (Bills)
│     ├── 2022
│     └── 2023
├── 30-39 Education
│ ├── 31 Primary School
│ │ ├── 31.01 Marks
│ │ ├── 31.02 5th Level
│ │ └── 31.03 6th Level
│ ├── 32 Secondary School
│ │ ├── 32.01 Marks
│ │ ├── 32.02 7th Level
│ │ ├── 32.03 8th Level
│ │ └── 32.04 9th Level
│ ├── 34 Apprenticeship Information Scientist
│ │ ├── 34.01 Marks
│ │ ├── 34.02 IPA
│ │ ├── 34.03 School
│ │ └── 34.04 <Company>
│ ├── 35 BMS
│ │ ├── 35.01 Marks
│ │ ├── 35.02 Documents
│ │ ├── 35.03 Biology
│ │ ├── 35.04 German
│ │ ├── 35.05 English
│ │ ├── 35.06 French
│ │ ├── 35.07 History
│ │ ├── 35.08 Math
│ │ ├── 35.09 Economics
│ │ ├── 35.10 Chemistry
│ │ └── 35.11 Physics
│ └── 36 Courses
│     ├── 36.01 Refactoring to Collections (2016)
│     ├── 36.02 Advanced Vue (2018)
│     └── 36.03 …
├── 40-49 Professional Work
│ ├── 41 Resumé
│ │ ├── 41.01 Archive
│ │ └── 41.02 Inspiration
│ ├── 42 <Company A> (20xx-20xx)
│ ├── 43 <Company B> (20xx-20xx)
│ ├── 44 <Company C> (20xx-20xx)
│ └── 45 <Company D> (20xx)
│     ├── 45.01 Contracts
│     └── 45.02 Salary Slips
├── 50-59 Media
│ ├── 51 Books & Papers
│ │ ├── 51.01 E-Book Library
│ │ ├── 51.02 Quotes and Highlights
│ │ ├── 51.03 Papers
│ │ └── 51.04 Manuals
│ ├── 52 Software
│ │ ├── 52.01 Apps
│ │ ├── 52.02 Games
│ │ └── 52.03 Magzine DVDs
│ ├── 53 Audio
│ │ ├── 52.01 Sounds
│ │ └── 52.02 Music Library
│ ├── 54 Videos
│ │ ├── 54.01 1 Second Everyday
│ │ ├── 54.02 TV Shows
│ │ ├── 54.03 Movies
│ │ ├── 54.04 Digitized DVDs
│ │ └── 54.05 Digitized VHS
│ ├── 55 Images
│ │ ├── 55.01 Wallpapers
│ │ ├── 55.02 App Icons
│ │ ├── 55.03 Terminal Inspiration
│ │ └── 55.04 Screenshots
│ ├── 56 Photos
│ │ ├── 56.01 Profile Pictures
│ │ ├── 56.02 Digitized Photo Albums
│ │ └── 56.02 Headers
│ └── 57 Eagle Libraries
│     ├── Architecture.library
│     ├── Eagle Auto Import
│     ├── Fashion.library
│     ├── Inspiration.library
│     └── Memes.library
├── 60-69 Writing
│ ├── 61 Notes
│ ├── 62 Recipes
│ │ ├── 62.01 Snacks
│ │ ├── 62.02 Dessert
│ │ ├── 62.03 Soup
│ │ └── 62.04 Bread
│ ├── 63 stefanzweifel.dev
│ │ ├── 63.01 Drafts
│ │ └── 63.02 Archive
│ ├── 64 Journal
│ │ ├── 2022
│ │ └── 2023
├── 70-79 Projects
│ ├── 71 Projects
│ │ ├── 71.01 <Project A>
│ │ ├── 71.01 <Project B>
│ │ └── 71.01 <Project C>
│ ├── 72 stefanzweifel.dev
│ │ ├── 72.01 Design
│ │ └── 72.02 Backup
│ └── 73 screeenly
│     ├── 73.01 Accounting
│     ├── 73.02 Design
│     ├── 73.03 Feedback
│     ├── 73.04 Pricing Decision
│     └── 73.05 Backups
├── 80-89 ~NOT IN USE~
└── 90-99 Archives
    ├── 91 Backups
    │ ├── 91.01 Hazel Rules
    │ ├── 91.02 PiHole Settings
    │ └── 91.03 Photo Library
    ├── 92 Archive
    │ ├── 92.01 <Photo Book A>
    │ ├── 92.02 <Photo Book B>
    │ ├── 92.03 Google <Account A>
    │ ├── 92.06 Reddit <Account A>
    │ └── 92.07 mastodon.social Account
    └── 93 Keepsakes

```

Phew! What a list, right?

As the tree-list alone is a bit overwhelming and maybe not as expressive, I would like to highlight some areas and categories and explain what I put in them.

(My structure is by no means perfect and while writing this posts I noticed some flaws or duplicate folders I would like to correct in the future.)

### General

What I noticed the most when I revised my structure, is that I needed to embrace the 99 available folders in a category more.

Previously, I tried too hard to come up with good area names and then put only 2-3 sub folders in each area. (So much wasted _number space_)

### 11 Personal

The folder I struggled most with. What are "personal" files even?

Right now it's basically a catch-all area that contains all documents related to me. Random letters I received over the years and I want to keep, documents related to my civil defence service, documents about cars or bikes I own or owned. Legal documents regarding apartments or insurances.

### "40-49 Professional Work" vs. "70-79 Projects"

A better name for "40-49 Professional Work" would be "Career" or "Employment". (When you're reading this blog post, I probably have already updated the folder name).

_"40-49"_ contains my CV and all files related to my employments over the last few years. I named it "Professional Work", as I wanted to distinguish between "work I'm being paid for" and "work I do in my free time".  
I thought "Professional Work" would contain maybe popular ongoing open source projects or paid side-projects. "Projects" would contain one-off projects like making a photo book for a family member or a poster print.

However, in the last 5 years I didn't pick up freelancing or did any other work outside of my employment. Files related to projects still all ended up in "70-79 Projects".

That's why I will rename _40-49_ to "Career" and make the structure simpler again.

### 60-69 Writing

As the name suggests, this folder contains all my writing. Drafts or finished blog posts, letters, various cooking recipes I developed over time, journals and a – currently – empty notes folder.

I switched to using Obsidian for my notes a couple of months ago, but haven't migrated my vault to this structure yet.

Moving my notes out of a `~/iCloud/Obsidian` folder prevents me from ever using Obsidian on my phone or tablet, but I never really needed that anyway.

If I need to write something down, I can create a note in iA Writer or create a task in Things. If I need to read a note, I can search my entire vault through iA Writer or use on-device search.

That's the joy of using plain text for your notes. You can read the content anywhere.

### Difference between Archive and Backup

Probably the biggest change to my previous setup is the stronger distinction between what belongs into the "Archive" and "Backup" folder.

"Archive" contains data that can't be imported into other systems or files I otherwise want to keep.  
For example PDF archives of essays or news paper articles I like; or account exports from various software services (Reddit, Spotify, etc.)

"Backup" on the other hand, contains data that I could import into software or that I could use to restore software into a particular state.

For example database backups for certain side projects; my entire photo library grouped by year, so that I could re-create a library in a new app; configuration files for software that don't have a sync service or can't be configured through dotfiles.

## Conclusion

I use _JD_ for a couple of years now and will use it for the forseeable future.

Migrating all my files to iCloud Drive was also a great move. It's such a pleasent surprise when I can say during a conversation: "Give me a sec. That trip should be in 14.×." and a few seconds later I can show them a travel inquiry for a trip I made years ago.

The only negative aspect of my setup is that I can't easily create a backup of my iCloud Drive.

There is a "Download Now" feature available in Finder, but iCloud will _intelligently_ remove the downloads after a couple of days or weeks to free up space. I also can't got to to icloud.com and download an archive of a specific folder nor can I use a HTTP API to generate a zip-archive.[3](#fn:3)

For now I create weekly incremental backups of the most important files using [BorgBackup](https://www.borgbackup.org/) and store them in two different physical locations.[4](#fn:4)

---

If I could spark an interest in Johnny Decimal check out [their website](https://johnnydecimal.com/).  
If you want to learn even more, I can recommend [purchasing their workbook](https://johnnydecimal.com/10-19-concepts/14-build-your-system/14.02-the-decimal-workbook/) which goes into even more detail and guides you through the whole process of setting up a new folder structure.

If you have any questions or suggestions, please let me know!

---

1. <https://www.theverge.com/22684730/students-file-folder-directory-structure-education-gen-z> [↩](#fnref:1)
2. I do have encrypted backups of all important files in a couple of places. But that's for another blog post. [↩](#fnref:2)
3. I still have hope that Apple will one day make such a feature available, but I also understand that features like "Advanced Data Protection" don't make that easy. [↩](#fnref:3)
4. I think my whole backup solution using Borg might also be something I should blog about. [↩](#fnref:4)

 © 2012 - 2024 Stefan Zweifel