---
id: 2df592f2-1e82-45f1-8ebe-cf0e1b5e7db9
site_name: Microsoft On the Issues
author: Clint Watts
date_published: 2024-06-03
date_saved: 2024-06-09
date_read: 2024-06-09
date_archived: 2024-06-09T08:08:24.000Z
original_url: https://blogs.microsoft.com/on-the-issues/2024/06/02/russia-cyber-bots-disinformation-2024-paris-olympics/
omnivore_url: https://omnivore.app/me/how-russia-is-trying-to-disrupt-the-2024-paris-olympic-games-mic-18ffc08971a
---

 - Site: Microsoft On the Issues
 - By: Clint Watts
 - Date published: 2024-06-03
 - Date read: [[2024-06-09]]
 - [Read Original](https://blogs.microsoft.com/on-the-issues/2024/06/02/russia-cyber-bots-disinformation-2024-paris-olympics/)
 - [Read on Omnivore](https://omnivore.app/me/how-russia-is-trying-to-disrupt-the-2024-paris-olympic-games-mic-18ffc08971a)
 - Tags:  #AI  #Misinformation  #Olympics  #Politics  #Russia 
 - Notes: 

**Note:** Below is the text from the article, with any ==highlights== done by me. None of the writing below is by me.

# Article text
![Paris Olympics sign on front of City Hall](https://proxy-prod.omnivore-image-cache.app/0x0,swdLXKW_azNOL5RSBxLXlcKfBuLZAZPMAtnS2XqYHhew/https://blogs.microsoft.com/wp-content/uploads/prod/sites/5/2024/05/Paris-2024.jpg) 

Russia is ramping up malign disinformation campaigns against France, French President Emmanuel Macron, the International Olympic Committee (IOC), and this summer’s Olympic Games in Paris. While Russia has a decades-long history of targeting the Olympic Games, the Microsoft Threat Analysis Center (MTAC) has observed old tactics blending with artificial intelligence (AI) in malign activity that may intensify as the 2024 Paris Opening Ceremony approaches. These operations have two principal aims:

* Denigrate the reputation of the IOC
* Create the expectation of violence breaking out in Paris at the Games

Several prolific Russian influence actors, which Microsoft tracks as Storm-1679 and Storm-1099, have pivoted their operations since June 2023 to focus on the Olympics. These insights are detailed in a special Microsoft Threat Intelligence report published today: “[_Russian Influence Efforts Converge on 2024 Paris Olympic Games_](https://aka.ms/OlympicsReport-June2024).”

#### **Olympics Has Fallen**

Olympics-focused activity kicked off in June 2023, when Storm-1679 released on Telegram and then spread online a feature-length film called “Olympics Has Fallen”, mimicking the 2013 American political action thriller “Olympus Has Fallen”. Using a fake AI-generated audio impersonating the actor Tom Cruise to imply his participation, the film disparaged the IOC leadership. The use of slick computer-generated special effects and a broad marketing campaign, including faked endorsements from Western media outlets and celebrities, indicates a significant increase in skill and effort compared to most Influence Operations (IO) campaigns.

[![](https://proxy-prod.omnivore-image-cache.app/507x294,sYpHO863eG5ZZvAWnZuzzGN4HkKfKfVxTY82p-VIeK3U/https://blogs.microsoft.com/wp-content/uploads/prod/sites/5/2024/05/olympdp1.jpg)](https://blogs.microsoft.com/wp-content/uploads/prod/sites/5/2024/05/olympdp1.jpg)

Figure 1: A visual from the fake documentary “Olympics Has Fallen”, produced by Russia-affiliated influence actor Storm-1679, which targets the International Olympic Committee and advances pro-Kremlin disinformation. The documentary uses the image and likeness of American actor Tom Cruise, who did not participate in any such documentary.

#### **Spreading fear of violence**

Storm-1679’s goals are not limited to defaming the IOC. It also seeks to spread public fear to deter spectators from attending the Games. Over the past year, it has consistently produced a collection of deceptive videos on the expectation of violence at the Games. Examples include:

* A video purporting to be from Brussels-based media outlet Euro News, claimed Parisians were buying property insurance in anticipation of terrorism at the Games.
* A fake video pretending to come from French broadcaster France24 claimed that 24% of tickets for the games had been returned due to fears of terrorism.
* Fake video press releases were produced posing as coming from the American Central Intelligence Agency (CIA) and the French General Directorate for Internal Security (DGSI) warning potential attendees to stay away from the Paris 2024 Olympics due to the alleged risk of a terror attack.  
[![A faked video press release warning the public of possible terror attacks at the 2024 Paris Summer Olympics (left). A fabricated France 24 news clip claiming that nearly a quarter of Paris 2024 tickets have been returned due to concerns over terrorism (right). Both forgeries were produced by Russia-affiliated actor Storm-1679.](https://proxy-prod.omnivore-image-cache.app/995x592,sISq0g9ELQj0hIktao3AtKMyVK8uPI2yyN9X53ZaO-B8/https://blogs.microsoft.com/wp-content/uploads/prod/sites/5/2024/05/olympdp2-1024x609.jpg)](https://blogs.microsoft.com/wp-content/uploads/prod/sites/5/2024/05/olympdp2.jpg)  
Figure 2: A faked video press release warning the public of possible terror attacks at the 2024 Paris Summer Olympics (left). A fabricated France 24 news clip claiming that nearly a quarter of Paris 2024 tickets have been returned due to concerns over terrorism (right). Both forgeries were produced by Russia-affiliated actor Storm-1679.
* Storm-1679 has also sought to use the Israel-Hamas conflict to fabricate threats to the Games. In November 2023, it posted images claiming to show graffiti in Paris threatening violence against Israeli citizens attending the Games. Microsoft assesses this graffiti was digitally generated and unlikely to exist at a physical location.
* Other images and videos referenced the 1972 Munich Olympics where members of Black September, a militant organization, killed 11 members of the Israeli Olympic team and a West German police officer. Microsoft does not presently have enough information to attribute the video to a specific actor, but its heavy amplification by pro-Russian bot accounts suggests the video may be another operation in the broader Olympics campaign.

[![portmanteau of two images described in caption](https://proxy-prod.omnivore-image-cache.app/885x328,sW2flGAlBF4FoaGhahdCN9HX4cwbDgnHeeH-qolyiXRs/https://blogs.microsoft.com/wp-content/uploads/prod/sites/5/2024/05/olympdpport.jpg)](https://blogs.microsoft.com/wp-content/uploads/prod/sites/5/2024/05/olympdpport.jpg)

Figure 3: An image of graffiti, reportedly left in Paris, threatening a repeat of the 1972 Munich terror attacks at the upcoming Olympic Games in Paris (left). A still image from the false-flag terror threat, purportedly from Turkish ultranationalist group the Grey Wolves, whose symbol is visible in the top-right corner of the screen. The video was widely publicized by pro-Russian bot accounts and prompted a response from the Israeli Olympic Committee (right).

**Other Russian threat actors are joining the fray**

Storm-1679 is not the only Russia-aligned actor seeking to undermine the 2024 Games. The Russia-affiliated actor that Microsoft tracks as Storm-1099, better known as “Doppelganger,” has ramped up its anti-Olympics messaging in the past two months. Using its array of 15 unique French language “news” sites, including its core disinformation outlet ==Reliable Recent News (RRN)==, it makes claims of rampant IOC corruption and warns of potential violence at the Games. The actor also makes forgeries of French outlets Le Parisien and Le Point to echo such claims and castigate Macron and his government, his supposed showmanship around the Games and his indifference to the hardships faced by French citizens.

[![A selection of fake news stories](https://proxy-prod.omnivore-image-cache.app/636x340,sJ7paK_rRUzc71gQcRActNAHQWicPhZPj5D6JFr_fZIk/https://blogs.microsoft.com/wp-content/uploads/prod/sites/5/2024/05/olympdp5.jpg)](https://blogs.microsoft.com/wp-content/uploads/prod/sites/5/2024/05/olympdp5.jpg)

Fig 4: A selection of Storm-1099’s anti-Olympics messaging, including from its core disinformation outlet Reliable Recent News (RRN).

#### **Looking forward**

With the Olympic Games opening ceremony less than three months away on July 26th, MTAC expects Russian Olympics-focused malign activity to intensify. Predominantly French-language activities will likely expand to English, German, and other languages to maximize visibility and traction online and the use of generative AI will also likely increase. While video has traditionally been a powerful tool for Russian IO campaigns and will remain so, we are likely to see a tactical shift towards online bots and automated social media accounts. These can offer the illusion of widespread support by quickly flooding social media channels and give the Russians a level of plausible deniability.

On the ground, Russian actors may look to exploit the focus on stringent security by creating the illusions of protests or real-world provocations, thus undermining confidence in the IOC and French security forces. In-person staging of events – whether real or orchestrated –near or around Olympic venues could be used to manipulate public perceptions and generate a sense of fear and uncertainty.

Microsoft remains committed to protecting the conduct and integrity of the 2024 Summer Olympic Games. MTAC will monitor and report on any campaigns stemming from Kremlin-backed actors in the lead up to and opening of the Paris Games.

Tags: [cyber influence](https://blogs.microsoft.com/on-the-issues/tag/cyber-influence/), [influence operations](https://blogs.microsoft.com/on-the-issues/tag/influence-operations/), [Microsoft Threat Analysis Center](https://blogs.microsoft.com/on-the-issues/tag/microsoft-threat-analysis-center/), [MTAC](https://blogs.microsoft.com/on-the-issues/tag/mtac/), [Russia](https://blogs.microsoft.com/on-the-issues/tag/russia/)