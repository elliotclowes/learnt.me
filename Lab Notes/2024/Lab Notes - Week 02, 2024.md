## Monday

### Folder lock-in

I've been reading about [[Johnny.Decimal]] and have been considering overhauling how and where I store my files. The only issue is that a lot of my files are being automatically moved via [Hazel](https://www.noodlesoft.com/). I have created lots of rules for auto-moving and backing things up and there's a lot of moving parts. Changing how my folders are organised would likely break most of those Hazel rules. So I'd need to update them. It wouldn't be *too* much of a pain. But it would be a pain nonetheless. I think I'll stick with my current system for now.

The main issue is that I have three main places where things are stored: `Backups`, `Files` and `Documents`. And a common issue is that when I need to check/save something in a sub-folder I can't remember in which of those three folders it lives.

On paper it should work like this:
- `Backups` - Backups of things like websites, software files, config files, bookmarks, etc.
- `Documents` - Nearly all PDF and Word files.
- `Files` - Assorted things that aren't documents. The contents of its sub-folders are 'active' and are often changing.

But in reality it doesn't always work like this. And I am getting too much cognitive load from having to think where something lives. There's certainly room for improvement.

### Read: [[Article — They Want You To Forget What A Film Looks Like - Aftermath]]

![[Article — They Want You To Forget What A Film Looks Like - Aftermath#My Notes]]

## Tuesday

### Todo list view

My todo list software of choice is [[Todoist]]. I've been using 'board' view for my work stuff. I've realised that I think I need to go to the 'list' view instead. There's something about the board view that just feels overwhelming to my brain and I don't know where start.

Also, sub-tasks are hidden until you click on the main task in the board view. This makes it a bit easier for me to forgot about them. They're out of sight, out of mind.

I decided to give the board view a go as that way I can have all my work todos in one Todoist project. And it did have its benefits. But overall I think I prefer list view.

**Board view:**
![](https://res.cloudinary.com/imagist/image/fetch/q_auto/f_auto/c_scale,w_2624/https%3A%2F%2Ftdinspiration.wpengine.com%2Fwp-content%2Fuploads%2F2020%2F10%2Ftodoist-board-todays-work-1.png)

**List view:**
![](https://res.cloudinary.com/imagist/image/fetch/q_auto/f_auto/c_scale,w_2624/https%3A%2F%2Ftdinspiration.wpengine.com%2Fwp-content%2Fuploads%2F2021%2F05%2F5_block-wide.png)

## Wednesday

### Too many backup locations

I've been thinking about how I need to condense my backups. At the moment they're spread over too many places and use too many bits of software to do.

These are my current devices
- MacBook Pro (MBP): my main computer.
- Mac mini (MM): essentially a server with some external hard drives attatched.
- Unraid: my main storage server where my media files live.
- Synology: this was replace by my Unraid server. However it currently isn't powering on, for some reason.

The software I use:
- [ChronoSync](https://www.econtechnologies.com/chronosync/overview.html): I use this to automate moving files from one device to another. But I've never been a big fan of it and I think half of the things it does it currently broken.
- rclone: this is a command line tool I use to manually move certain folders from Unraid to the Mac mini.
- [Arq](https://www.arqbackup.com/): this backups files from the MacBook and Mac mini to Amazon S3 and Google Drive.
- [Backblaze](https://www.backblaze.com/): this backups the hard drives attached to the Mac mini.
- [Dropbox](https://www.dropbox.com/): installed on my MacBook and Mac mini. The Mac mini's internal hard drive isn't large enough to store all my Dropbox files, so it only has some. So my Macbook is where all the Dropbox files live (as well as on the Dropbox servers of course).

The problem is that things are backed up all over the place. And some backups are automated and some aren't. I think the main issue is that I have too much data. Although I would say I have three 'kinds' of data, which should make things easier:
- Non-personal media files: things like movies, TV and music. 
- Personal media files: photos and videos.
- 'Documents': this is personal things like documents, notes, backups of software, and audio recordings.

'Non-personal media files' makes up probably 95% of storage used. It's BluRays and CDs I've ripped and things like that. If I loose them it's not the end of the world. But I'd avoid it if possible.

'Personal media files'. This is probably about 1TB of data. I can never lose this stuff.

'Documents'. This is about 160GB of data. To be honest, my life wouldn't end if this disappeared. But again, I'd like to avoid it.

I won't go into how it's currently all stored and backed up. But this is my current plan.

- **'Documents'**
	- Main location: MacBook Pro
	- Local backups: Unraid
	- Cloud backups: Dropbox + Google Drive (via Arq on MBP) + Amazon S3 (via Arq on MBP) + Backblaze (on MM)
- **'Personal media files'**
	- Main location: Mac mini (external hard drive)
	- Local backups: Unraid
	- Cloud backups: Dropbox (on MM) + Backblaze (on MM) + Google Drive (via Arq on MM) + Amazon S3 (via Arq on MM)
- **'Non-personal media files'**
	- Main location: Unraid
	- Local backups: Mac mini (external hard drive)
	- Cloud backups: Backblaze (on MM)