
## Switched from Dropbox to Syncthing
[[2024-10-07]]
I'm trying to switch from Dropbox to Syncthing. It will sync between my MacBook Pro, Mac mini and Zola (Unraid server). The data won't be accessible remotely on my phone.

## [[Seafile]]
[[2024-10-04]]
I tried this out. It was easy to set up. The UI is rather outdated. But I didn't really look too much into it as I couldn't download files (I think). They just wouldn't download in the browser.

## Getting rid of Dropbox, Backblaze, Linode and my small dedicated server
[[2024-10-04]]

I decided to try and combine some services I run or use into one. At the moment I have these:
- **Dropbox**. For file syncing, backups and accessing of files on my phone.
- **Backblaze**. For backing up files.
- **Linode**. VPN and online radio station.
- **Dedicated server**. For transcoding film and TV shows, and downloading files.

The dedicated server isn't good enough for my needs. Its CPU has a passmark c. 4000, meaning transcoding takes a long time – especially 4K content. And it only has 1 TB of space. So I'm forever having to manage space.

The dedicated server I want is a lot more. €45/mo instead of my current €11.50/mo. So just justify that I need to use that €45 one for more than just transcoding. So I need to be able to cancel £10/mo Dropbox, £5/mo Linode and £8.20/mo Backblaze.

Here's my plan how |'ll .
- **Dropbox**. This is the toughest one to replace. There's lots of software for backing things up. Not many have good mobile apps. Nor do they have nice file version history features. Still not sure.
- **Backblaze**. Easy enough. The files backed up to Backblaze will be sent to the big dedicated server instead. I need the files to be encrypted though.
- **Linode**. The VPN and online radio station are on a Ubuntu server already. I'll just run them on the new one instead.


