---
id: 48fdceec-bdb4-441e-a75d-c1437e55ce49
site_name: sive.rs
date_published: 2024-02-27
date_saved: 2024-10-02
date_read: 2024-10-03
date_archived: 2024-10-03T06:03:17.000Z
original_url: https://sive.rs/backup
omnivore_url: https://omnivore.app/me/how-i-backup-derek-sivers-18dea2377a5
---

 - Site: sive.rs
 - By: 
 - Date published: 2024-02-27
 - Date read: [[2024-10-03]]
 - [Read Original](https://sive.rs/backup)
 - [Read on Omnivore](https://omnivore.app/me/how-i-backup-derek-sivers-18dea2377a5)
 - Tags:  #Technology  #Backups 
 - Notes: 

**Note:** Below is the text from the article, with any ==highlights== done by me. None of the writing below is by me.

# Article text
<DIV id="readability-content"><DIV data-omnivore-anchor-idx="1" class="page" id="readability-page-1"><article data-omnivore-anchor-idx="2">


<p data-omnivore-anchor-idx="3">
Some people have asked, so here is how I do my backups.
It takes me about <strong data-omnivore-anchor-idx="4">ten seconds per day</strong> and <strong data-omnivore-anchor-idx="5">five minutes per month</strong> to maintain.
</p><p data-omnivore-anchor-idx="6">
It works well for me, but I’m always open to suggestions.
Just <a data-omnivore-anchor-idx="7" href="https://sive.rs/contact">email me</a> with any ideas or questions.
</p>

<h2 data-omnivore-anchor-idx="8">every-day documents (~40 GB)</h2>
<p data-omnivore-anchor-idx="9">
Files I use and change every day: documents, emails, code, diary, ideas, website, accounts, etc.
</p>
<ul data-omnivore-anchor-idx="10"><li data-omnivore-anchor-idx="11">
I have a desktop and a laptop, so I keep this ~40 GB directory cloned with rsync every day or so between them.
Whenever I turn on one computer, I sync it from the other.
</li><li data-omnivore-anchor-idx="12">
Daily rsync to an encrypted Linux USB stick attached to the desktop.
</li><li data-omnivore-anchor-idx="13">
Daily rsync to an encrypted MacOS USB stick attached to the laptop.
</li><li data-omnivore-anchor-idx="14">
Daily rsync to an encrypted ZFS SSD inside the desktop.
</li><li data-omnivore-anchor-idx="15">
Daily rsync to OpenBSD remote attached storage at vultr.com as <a data-omnivore-anchor-idx="16" href="https://sive.rs/ti">described at my “Tech Independence” page</a>.
</li></ul>
<p data-omnivore-anchor-idx="17">
I’ve written shortcuts for these rsync commands so it’s really as simple as me typing <code data-omnivore-anchor-idx="18" class="hljs language-ebnf"><span data-omnivore-anchor-idx="19" class="hljs-attribute">bkz</span></code> or <code data-omnivore-anchor-idx="20" class="hljs language-ebnf"><span data-omnivore-anchor-idx="21" class="hljs-attribute">bkstick</span></code> in the terminal as I’m working anyway.
I do it a few times a day, especially if I’ve just made or saved something of value.
And always right before I shut down the computer, which I do almost any time I step away from it for more than a few minutes.
That’s why I say it’s like ten seconds a day, just typing that command occasionally.
</p>

<h2 data-omnivore-anchor-idx="22">keepsakes (~3 TB)</h2>
<p data-omnivore-anchor-idx="23">
Rarely-accessed files I want to keep forever: videos and photos of my kid, music and film collection.
</p>
<ul data-omnivore-anchor-idx="24"><li data-omnivore-anchor-idx="25">
Three different external 4TB 2.5" drives, in three different formats: ZFS, OpenBSD, MacOS.
</li><li data-omnivore-anchor-idx="26">
Every month or so, I connect them via USB cable, and rsync everything to each of them, bringing one down to a safe deposit box downtown, and taking out the one that was there from my last visit.
</li><li data-omnivore-anchor-idx="27">
5TB at <a data-omnivore-anchor-idx="28" href="https://www.hetzner.com/storage/storage-box">Hetzner Storage Box</a>, I rsync remotely.
</li><li data-omnivore-anchor-idx="29">
4TB at <a data-omnivore-anchor-idx="30" href="https://zfs.rent/">ZFS.rent</a>, a ZFS encrypted clone.
</li></ul>
<p data-omnivore-anchor-idx="31">
So that’s five copies of my keepsakes in four different locations.
Each one also has a recent copy of my every-day documents from above.
So a few minutes a month to connect the USB drives, and I only do the safe deposit box when I’m going that way anyway, and only takes a couple minutes.
</p><p data-omnivore-anchor-idx="32">
In the days of spinning-platter hard drives, they used to die surprisingly often, so I like the security of many copies.
But it also helps to have some deliberately behind others, so on the rare case where I’ve deleted something, then rsynced my dailies and even my monthly, then realized I need that thing I deleted, then I know the drive in the safe deposit box has it since I haven’t updated that one in a couple months.
</p>


</article></DIV></DIV>