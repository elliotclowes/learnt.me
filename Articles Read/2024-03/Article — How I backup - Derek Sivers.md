---
id: 48fdceec-bdb4-441e-a75d-c1437e55ce49
site_name: sive.rs
date_published: 2024-02-27
date_saved: 2024-03-07
date_read: 2024-03-07
date_archived: 2024-03-07T08:11:02.000Z
original_url: https://sive.rs/backup
omnivore_url: https://omnivore.app/me/how-i-backup-derek-sivers-18dea2377a5
---

 - Site: sive.rs
 - By: 
 - Date published: 2024-02-27
 - Date read: [[2024-03-07]]
 - [Read Original](https://sive.rs/backup)
 - [Read on Omnivore](https://omnivore.app/me/how-i-backup-derek-sivers-18dea2377a5)
 - Tags:  #Technology  #Backups 
 - Notes: 

**Note:** Below is the text from the article, with any ==highlights== done by me. None of the writing below is by me.

# Article text
Some people have asked, so here is how I do my backups. It takes me about **ten seconds per day** and **five minutes per month** to maintain.

It works well for me, but I’m always open to suggestions. Just [email me](https://sive.rs/contact) with any ideas or questions.

## every-day documents (\~40 GB)

Files I use and change every day: documents, emails, code, diary, ideas, website, accounts, etc.

* I have a desktop and a laptop, so I keep this \~40 GB directory cloned with rsync every day or so between them. Whenever I turn on one computer, I sync it from the other.
* Daily rsync to an encrypted Linux USB stick attached to the desktop.
* Daily rsync to an encrypted MacOS USB stick attached to the laptop.
* Daily rsync to an encrypted ZFS SSD inside the desktop.
* Daily rsync to OpenBSD remote attached storage at vultr.com as [described at my “Tech Independence” page](https://sive.rs/ti).

I’ve written shortcuts for these rsync commands so it’s really as simple as me typing `bkz` or `bkstick` in the terminal as I’m working anyway. I do it a few times a day, especially if I’ve just made or saved something of value. And always right before I shut down the computer, which I do almost any time I step away from it for more than a few minutes. That’s why I say it’s like ten seconds a day, just typing that command occasionally.

## keepsakes (\~3 TB)

Rarely-accessed files I want to keep forever: videos and photos of my kid, music and film collection.

* Three different external 4TB 2.5" drives, in three different formats: ZFS, OpenBSD, MacOS.
* Every month or so, I connect them via USB cable, and rsync everything to each of them, bringing one down to a safe deposit box downtown, and taking out the one that was there from my last visit.
* 5TB at [Hetzner Storage Box](https://www.hetzner.com/storage/storage-box), I rsync remotely.
* 4TB at [ZFS.rent](https://zfs.rent/), a ZFS encrypted clone.

So that’s five copies of my keepsakes in four different locations. Each one also has a recent copy of my every-day documents from above. So a few minutes a month to connect the USB drives, and I only do the safe deposit box when I’m going that way anyway, and only takes a couple minutes.

In the days of spinning-platter hard drives, they used to die surprisingly often, so I like the security of many copies. But it also helps to have some deliberately behind others, so on the rare case where I’ve deleted something, then rsynced my dailies and even my monthly, then realized I need that thing I deleted, then I know the drive in the safe deposit box has it since I haven’t updated that one in a couple months.