**An overview of my digital life**

I’m a big fan of [The Setup](http://usesthis.com/). It’s “a collection of nerdy interviews asking people from all walks of life what they use to get the job done.” So in the spirit of it, I’ve decided to do my own. You can can see previous editions: [2013](https://imlefthanded.com/2014/the-setup-of-2013/), [2014](https://imlefthanded.com/2015/the-setup-of-2014/) and [2016](https://imlefthanded.com/2017/the-setup-of-2016/).^[My initial plan was to do a new one each year, but s you can see I have failed in my duty. So from now I think I'll just update this page as and when changes occur.]

## Hardware

My main computer is a MacBook Pro (15-inch, 2019) with 16GB of RAM and a 256GB SSD. I pair it with a [Logitech M570](https://www.amazon.co.uk/Logitech-Wireless-Mouse-Trackball-Windows/dp/B0042BBR2S?th=1) trackball. I really like trackballs because they play nicely with my [RSI](https://www.nhs.uk/conditions/repetitive-strain-injury-rsi/) and they can be used on any surface, unlike a mouse.

When working at my desk my laptop is connected to a [Apple Thunderbolt Display](https://web.archive.org/web/20130723232749/http://www.apple.com/uk/displays/specs.html), [Happy Hacking Keyboard Professional 2](https://www.hhkeyboard.com/uk/products/pro2), another Logitech M570 trackball and some ancient Bose computer speakers. The desk I use is a [IKEA Skarsta sit/stand one](https://www.ikea.com/gb/en/p/skarsta-desk-sit-stand-white-s59324818/). ^[Though I now never use the standing functionality of the desk. I purchased it when I was suffering from sciatica. But now thankfully my sciatica is minor and doesn't bother me too much, and I now  prefer to sit than stand as standing can tire my back. Also, to lower/raise the desk you have to manually crank it, which is a massive annoyance. My advice if you want a sit/stand desk is to get a fancy electric one. They're expensive, but worth it. The only reason to get a non-electric one is if you plan on almost never changing it from sit to stand mode.]

I also have an [iPad Pro](https://web-beta.archive.org/web/20151113192950/https://www.apple.com/ipad-pro/) (12.9 inch).^[I purchased it refurbished from Apple. And the fact that I forgot about that fact until I wrote this article speaks volumes for how reliable it has been. Don't be shy about buying refurbished!] Which is mostly a glorified [Instapaper](https://www.instapaper.com/) toilet reading device.

I'm not a huge gamer^[The only games I really play are online first person shooters. Mainly the [Battlefield franchise](https://en.wikipedia.org/wiki/Battlefield_(video_game_series)). However the past two releases in the series ([Battlefield V](https://en.wikipedia.org/wiki/Battlefield_V) and [Battlefield 2042](https://en.wikipedia.org/wiki/Battlefield_2042)) have been pretty rough. So I'm still playing 2016's [Battlefield 1](https://en.wikipedia.org/wiki/Battlefield_1), which is one my favourite games ever.] but do I have a a PlayStation 5 and PlayStation 4 slim.

### Servers

I have a self-built home server (named *Zola*^[I name all my servers after old players of [Chelsea Football Club](https://en.wikipedia.org/wiki/Chelsea_F.C)] which was mainly built to run Plex. Its OS is [unRAID](https://unraid.net/), and it has a [AMD Ryzen 7 1700](https://www.amd.com/en/products/cpu/amd-ryzen-7-1700) CPU, 16GB of RAM, a [500GB SSD](https://www.amazon.co.uk/dp/B073SBX6TY?tag=pcp0f-21&linkCode=ogi&th=1&psc=1), 44TB of useable storage, and is housed in a [Fractal Design Define R5 Blackout Edition](https://www.fractal-design.com/products/cases/define/define-r5/black/) case.

Another server I have is a [Synology DS1815+ NAS](https://www.storagereview.com/review/synology-diskstation-ds1815-review), with 24TB of storage. This was my main server until *Zola* came along, so its function now is as a backup server. It's about half the size of *Zola* so only key files are backed up here and it also serves as a [Time Machine backup](https://en.wikipedia.org/wiki/Time_Machine_(macOS)) to my MacBook via two 1TB drives in [RAID 1](https://en.wikipedia.org/wiki/Standard_RAID_levels#RAID_1).

There's also an old Mac mini server (late 2014, 2.6GHz Dual-Core Intel Core i5, 8GB RAM, 500GB SSD) I have running which is another piece of hardware that's been superseded by *Zola* and that I should probably sell. Its only real job these days is backing up files I have on an external hard drive to [Backblaze](https://www.backblaze.com/).

I also rent a server in the cloud from [Scaleway](https://www.scaleway.com/en/dedibox/). It has a Intel Xeon E3-1230 v2, 16GB of RAM and 2x1TB HDD's. I mainly use it as a VPN (via [openvpn-install](https://github.com/Nyr/openvpn-install)), a backup server (via [SyncThing](https://syncthing.net/)) and also as a place to indulge in my video transcoding habit (via [Handbrake](https://hub.docker.com/r/jlesage/handbrake)).

### Network

My broadband is a 500 Mbps connection provided by [Virgin Media](https://www.virginmedia.com/broadband/broadband-only). It's been a pretty solid line and I've received several free speed upgrades down the years as they've upgraded their network. They provide a router but it's not great though,^[And of course ugly, black and large, as all ISP routers are required to be.] so it's just in dumb modem mode, with a [ASUS RT-N66U](https://www.amazon.co.uk/gp/product/B005T3TIBK/?th=1) doing all the actual router-y stuff. There's then a [TP-Link 24-Port switch](https://www.amazon.co.uk/gp/product/B000RSTX9O/) which then provides the connection to various wired devices.^[I still *much* prefer wired to wireless - despite all the advances in wireless technology down the years. If it *can* be wired, I *want* it wired. Unless a nibbling rat somehow gets involved, an ethernet cable will almost never let you down or experience the drop-outs or speed drops you will get with WiFi.]

I have a [Raspberry Pi 2](https://www.amazon.co.uk/dp/B00T2U7R7I/ref=pe_385721_37986871_TE_item) too. It mostly just runs [Pi-Hole](https://pi-hole.net/), which is a software that blocks ads and dodgy URLs for me. I like it because its network-wide. Ad blocking browser extensions are great, but they have to be installed on each individual device and not all devices even support them. Pi-Hole bypasses all that by being the DNS server on my home network and blocking stuff at source.

Wireless networking in my house has been a huge thorn in my sides for years. There's sadly something in the walls that seriously hinders any sort of WiFi signal from getting through.

And instead WiFi is handled by a Ubiquiti [UniFi AP AC Long Range](https://www.ui.com/unifi/unifi-ap-ac-lr/), which despite being 'long range' doesn't provide coverage to a room about 10 meters away. So to extend the coverage there's also another [UniFi AP AC](https://www.ui.com/unifi/unifi-ap-ac-lite/),^[The Lite version this time though.] with a powerline ethernet adapter^[[Arthur C. Clarke](https://en.wikipedia.org/wiki/Arthur_C._Clarke) [said](https://lab.cccb.org/en/arthur-c-clarke-any-sufficiently-advanced-technology-is-indistinguishable-from-magic/) that "any sufficiently advanced technology is indistinguishable from magic". And to me, powerline ethernet adapters are very much magic. [Here's a video](https://www.youtube.com/watch?v=ywQeJCa3jl8) on how they do actually work though if you're interested.] providing its ethernet connection.

### Smart home

Talking of the Raspberry Pi, I also experimented with running [Home Assistant](https://www.home-assistant.io/) on the Pi as well. But right now I don't have enough home automation products in use to warrant the use of the software and it felt like overkill. These days I just use [Alexa](https://en.wikipedia.org/wiki/Amazon_Alexa) to control the lights around my house.

### Home Entertainment

My TV is an [LG 55" 4K OLED](https://www.lg.com/uk/tvs/lg-OLED55B9PLA). I like it. It's my first OLED and 4K TV. I'm very much sold on 4K. The increased resolution over HD is great, and I do sit close enough to my TV and have sharp enough eyes to notice it. But the real killer feature is not the 4K, but the HDR colours. They're great. It's great fun rewatching some of my favourite movies of old when they come out on 4K Blu-Ray.^[Well, usually it is. Some 4K Blu-Ray releases of older movies aren't always perfect. Often colours are changed fairly significantly to showcase HDR in a gimmicky way. So much so that it does concern me that it has wandered too far from the director and colourists original vision.]

My streamer of choice is an [NVIDIA Shield TV Pro](https://www.nvidia.com/en-gb/shield/shield-tv-pro/). It's a remarkably powerful thing, but sadly the Plex app for it is atrociously buggy (and always has been) and now (after an unrejectable update) the home screen features huge ads. So overall, I would recommend a [Roku](https://www.roku.com/en-gb/products/streaming-stick-plus) instead. I have Roku's for all the other televisions in my house and they are small, reliable and simple. And whilst not as powerful as the Shield they run great and never crash. And the remote is great. Insanely long battery life, simple and they don't seem to acquire grime or lose their shine. All my heavily-used remotes look as good as they day I bought them. The only things I don't like about the Roku is its slow YouTube app and the its lack of ethernet.


## Software

### Backups

I have around 50 TB of data and that can make backups difficult and expensive. It's tough backing it up locally because whilst storage is getting cheaper and cheaper having a byte-for-byte copy of 50 TB is still pricey. And tough backing it up remotely as most 'unlimited' online backup services don't allow you to backup NAS's or servers. Also whilst my upload speed is now an _okay_ 50 Mbps it would still take me many months to upload all my data. So compromises and difficult decisions have to be made. It's made easier – but also more messy – by the fact that I have quite a bit of old hardware knocking around. So my backup solution is a little bit hodgepodge.

The files on my laptop are synced via [Resilio Sync](https://www.resilio.com/individuals/)^[Resilio Sync has been in my setup for a few years now. It it used way too much CPU. But I still like it. It's reliable and does the thing that all good backup solutions should do: just work.] to my unRAID server, [Synology DS1815+ NAS](https://www.storagereview.com/review/synology-diskstation-ds1815-review) and Mac mini. The Mac mini then backs it up to [Backblaze](https://backblaze.com)^[I like Backblaze. Its software is a bit ugly and janky (on the Mac anyway). But it's a good service. And the fact that they can send you a hard drive full of your data is great. A big issue with all backup services is getting your files back in a timely manner if you ever experience data loss locally. [Sneakernet](https://en.wikipedia.org/wiki/Sneakernet) is tough to beat.], [Google Drive](https://drive.google.com/) and also [Amazon S3 Glacier](https://aws.amazon.com/s3/storage-classes/glacier/)^[I'm not mad on Glacier. Firstly I've had mixed results with the Glacier/Arq combo. And man oh man is it expensive to get your data _back_. However it is cheap. So I have it in my setup just in case.] via [Arq](https://www.arqbackup.com/). [Time Machine](https://support.apple.com/en-gb/HT201250) also backups my laptop to the Synology^[The Time Machine / Synology combo is shockingly reliable.] a second time as it has file version history, which Resilio Sync lacks.

Slightly less important data is backed up to a 8 TB external hard drive connected to the Mac mini. From there it's backed up remotely to [Backblaze](https://backblaze.com). That 8 TB doesn't change too often so it's synced to that external drive 'by hand'. Though I should probably automate it, as something I've learnt is how vital it is automate backups. It's far too easy to just forget for a couple of months otherwise.

Less important data is sent to the 24 TB [Synology](https://www.storagereview.com/review/synology-diskstation-ds1815-review) with the data being synced over to it in the wee small hours of the night via [ChronoSync](https://www.econtechnologies.com/chronosync/overview.html). It's then sent to [Google Drive](https://drive.google.com/) via [Arq](https://www.arqbackup.com/). The Google Drive account is an old grandfathered-in Workspace 'unlimited' one and I fully expect it to be cancelled at some point, which I'm prepared for.^[I've been on the internet and using its backup services long enough to not take seriously and rely on any one which appears too good to be true. There's a rule when it comes to them: the moment you _finally_ finish backing up all those TB the company will restrict or remove it. The reason my Google Drive account has been functioning for as long as it has is because it's subsidised by Google. It will be a shame when it goes though, as it's always given me the fastest download speeds when restoring my data.]

## My Desk Down The Years

I've cobbled these images together from various random photos I've taken of my desk down the years. I probably should have implemented some sort of system where I took one each year with a proper camera and after tidying my desk. But alas, I didn't. So these will have to do.

### 2021
![[desk-2021-800.jpg]]

### 2020
![[desk-2020-800.jpg]]

### 2014
![[desk-2014-uni-800.jpg]]

### 2013
![[desk-2013-800.jpg]]

### 2012
![[desk-2012-800.jpg]]

### 2009
![[desk-2009-800.jpg]]

### 2008
![[desk-2008-800.jpg]]