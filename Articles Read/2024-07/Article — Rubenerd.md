---
id: bfb4ebbd-8f6e-4280-8833-157fda745b43
site_name: rubenerd.com
author: Ruben Schade
date_published: 2024-07-19
date_saved: 2024-07-21
date_read: 2024-07-21
date_archived: 2024-07-21T08:10:45.000Z
original_url: https://rubenerd.com/the-day-the-crowdstrike-died/
omnivore_url: https://omnivore.app/me/https-rubenerd-com-the-day-the-crowdstrike-died-190d4576f99
---

 - Site: rubenerd.com
 - By: Ruben Schade
 - Date published: 2024-07-19
 - Date read: [[2024-07-21]]
 - [Read Original](https://rubenerd.com/the-day-the-crowdstrike-died/)
 - [Read on Omnivore](https://omnivore.app/me/https-rubenerd-com-the-day-the-crowdstrike-died-190d4576f99)
 - Tags:  #Technology 
 - Notes: 

**Note:** Below is the text from the article, with any ==highlights== done by me. None of the writing below is by me.

# Article text
## [The day the CrowdStrike died](https://rubenerd.com/the-day-the-crowdstrike-died/)

_Drove my Chevy to the levee, but then it wouldn’t start because it received a borked software update._

I… where do you even start!?

We all just witnessed one of—if not the biggest—IT outages in history. I say _witnessed_ in the past tense, but the repairs and fallout from this will likely take months, if not longer. CrowdStrike has now usurped SolarWinds as the CamelCased cautionary tale Windows engineers will use when arguing about robust architectures and contingency plans.

For those reading this in my dusty future archives, yesterday at 16:00 Australia time was the moment CrowdStrike’s Falcon product pushed a broken kernel update to Windows machines across the planet, causing them to restart, blue screen, and become inoperable.

Windows is already a rough enough environment to administer, but this is only slightly above a worst-case scenario. Errors in the boot process require manual intervention, and either out-of-band or physical access to fix. I learned yesterday that a shocking number of servers and providers simply don’t have the former; hence the unfolding disaster as this patch rolled out and crashed machines across the planet. NTFS isn’t the most robust of file systems either, so I’m expecting a lot of secondary data loss issues to come out in the coming weeks.

News outlets and social media were flooded with pictures of inoperable computers from airports to supermarkets. Our local Aldi was running fine Friday afternoon, but Clara caught site of at least one broken terminal at our local Coles:

![A BSOD on a terminal in a local supermarket](https://proxy-prod.omnivore-image-cache.app/0x0,sDIiRJ16atO0A7O2xDo2TSRR5wbfmaFBO8od32ka3TOk/https://rubenerd.com/files/2024/crowdstrike-bsod@1x.jpg)

The local Sony store also closed, citing an inability to process sales:

![A sign outside the Sony store reading: experiencing technical difficulties, and unable to process sales currently. Sorry for the incovnenience.](https://proxy-prod.omnivore-image-cache.app/0x0,sdILsDQLLDXb4EFDS0gomBxh9l24TGfIY3p3ReuHqmVo/https://rubenerd.com/files/2024/crowdstrike-store@1x.jpg)

My first thought went out to the sysadmins around the world who suddenly either didn’t have a weekend, or would be working frantically most of their Friday to bring systems back online. Big outages like this have the advantage of public awareness, but clients are still going to complain loudly to their MSPs and IT teams when they can’t use their computers. They don’t care if you say “it’s CrowdStrike”.

There are bigger lessons about the production use of Windows, and how appropriate it is for third-parties to inject kernel-level features. I used to run a Tumblr with Windows boot errors in what I called inappropriate places, but this OS is entrenched and everywhere. Microsoft are not blameless here, as some news outlets and indignant social media users have suggested.

It’s also worth thinking about the person who pushed that patch, and is now watching the same news we are. We’ve all done something against an IT system that gave us that gut-wrenching feeling; mine was forgetting to start a transaction and overwriting every client’s email addresses in a production database. Hey, I learned our backups worked! It’s easy to ascribe blame to an individual, but such circumstances are the end result of a chain of failed processes and decisions that should have prevented the problem, caught it, or had adequate safeguards in place. CrowdStrike’s management have a lot to answer for, and they’d damned well not take the opportunity to scapegoat.

_(I originally had some conjecture here about not being surprised if an AI tool wrote some code, but this seems unlikely. The patch was full of zeroes)._

I’d wondered what a planet-wide outage would look like, and from where it would come. Just like the unfolding climate change catastrophe, the end didn’t come from a targeted attack, but from malaise and incompetence. It’s more than a little ironic that a security vendor would be responsible, but also not that surprising.

`#hugops` to all the engineers who continue to scramble and fix this issue everywhere ☕️ 🥃. I hope you get some well-deserved time off after this.

---

---