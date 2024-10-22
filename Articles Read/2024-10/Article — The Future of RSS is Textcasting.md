---
id: 30e131a2-61d3-4924-8f31-e90c51d8cfe0
site_name: kottke.org
date_published: 2023-11-03
date_saved: 2024-10-13
date_read: 2024-10-22
date_archived: 2024-10-22T08:16:25.000Z
original_url: https://kottke.org/23/11/the-future-of-rss-is-textcasting-1
omnivore_url: https://omnivore.app/me/the-future-of-rss-is-textcasting-1928752ee4e
---

 - Site: kottke.org
 - By: 
 - Date published: 2023-11-03
 - Date read: [[2024-10-22]]
 - [Read Original](https://kottke.org/23/11/the-future-of-rss-is-textcasting-1)
 - [Read on Omnivore](https://omnivore.app/me/the-future-of-rss-is-textcasting-1928752ee4e)
 - Tags:  #Fediverse  #RSS  #Technology  #The_Web 
 - Notes: 

**Note:** Below is the text from the article, with any ==highlights== done by me. None of the writing below is by me.

# Article text
<DIV id="readability-content"><DIV data-omnivore-anchor-idx="1" class="page" id="readability-page-1"><div data-omnivore-anchor-idx="2" id="content-container">
<p data-omnivore-anchor-idx="3">

posted  by <a data-omnivore-anchor-idx="4" href="http://snarkmarket.com/">Tim Carmody</a><span data-omnivore-anchor-idx="5">  ·  <span data-omnivore-anchor-idx="6">gift link</span></span>



</p>




<p data-omnivore-anchor-idx="7"><img data-omnivore-anchor-idx="8" data-omnivore-original-src="https://kottke.org/cdn-cgi/image/format=auto,fit=scale-down,width=1200,metadata=none/plus/misc/images/RSS%20widescreen.jpeg" src="https://proxy-prod.omnivore-image-cache.app/820x430,sAM_kXFaWVjDWrrtPQjbhD__h0v1pc58OouoLIla-T54/https://kottke.org/cdn-cgi/image/format=auto,fit=scale-down,width=1200,metadata=none/plus/misc/images/RSS%20widescreen.jpeg" srcset="https://proxy-prod.omnivore-image-cache.app/500x0,s-RclEiD0Dua4klsI3OS6ICyJcyhCTtboV-Gc2SuRpNY/https://kottke.org/cdn-cgi/image/format=auto,fit=scale-down,width=500,metadata=none/plus/misc/images/RSS%20widescreen.jpeg 500w,https://proxy-prod.omnivore-image-cache.app/1200x0,svNBlu9VVksf-GBW4zM2-SXr7Y7Yy5xM024kBx6EwE9s/https://kottke.org/cdn-cgi/image/format=auto,fit=scale-down,width=1200,metadata=none/plus/misc/images/RSS%20widescreen.jpeg 1200w," sizes="(max-width: 500px) 500px, 1200px" loading="lazy" width="820" height="430" alt="RSS widescreen.jpeg"></p>

<p data-omnivore-anchor-idx="9">Earlier this week, Dave Winer (the inventor of RSS and lots of other notable software, and one of the earliest bloggers) made <a data-omnivore-anchor-idx="10" href="http://scripting.com/2023/10/31.html" target="_blank">a podcast for me</a>. He posted it publicly, so it wasn’t sealed like a letter, but it was addressed to me and responding to <a data-omnivore-anchor-idx="11" href="https://www.threads.net/@timcarmody/post/CzEd8Sap2Or?hl=en" target="_blank">something I wrote on Threads</a>. I don’t think I’ve ever been the personal addressee of a podcast before: like an @-reply, but in audio.</p>

<p data-omnivore-anchor-idx="12">For some reason, it reminded me of the poet Frank O’Hara’s “Personism” manifesto:</p>

<blockquote data-omnivore-anchor-idx="13"><p data-omnivore-anchor-idx="14">[Personism] was founded by me after lunch with LeRoi Jones on August 27, 1959, a day in which I was in love with someone (not Roi, by the way, a blond). I went back to work and wrote a poem for this person. While I was writing it I was realizing that if I wanted to I could use the telephone instead of writing the poem, and so Personism was born. It’s a very exciting movement which will undoubtedly have lots of adherents. It puts the poem squarely between the poet and the person, Lucky Pierre style, and the poem is correspondingly gratified. The poem is at last between two persons instead of two pages. In all modesty, I confess that it may be the death of literature as we know it.</p></blockquote>

<p data-omnivore-anchor-idx="15">But this is a digression. The ideas Dave is talking about in this podcast are serious (even if he is laughing a lot), and he spells them out in text at a site called <a data-omnivore-anchor-idx="16" href="http://textcasting.org/" target="_blank">Textcasting.org.</a> Here’s the philosophy:</p>

<blockquote data-omnivore-anchor-idx="17"><ul data-omnivore-anchor-idx="18"><li data-omnivore-anchor-idx="19">The goal is interop between social media apps and the features writers need.</li>

<li data-omnivore-anchor-idx="20"><strong data-omnivore-anchor-idx="21">What we’re doing: </strong>Moving documents between networked apps. We need a set of common features in order for it to work. </li>

<li data-omnivore-anchor-idx="22">The features are motivated by the needs of writers. Not by programmers or social media company execs.</li></ul></blockquote>

<p data-omnivore-anchor-idx="23">It’s a proposal to build, using technologies we already have and understand very well, a very simple social media protocol that is completely agnostic about what editor you use to write your posts and what viewer you choose to read it. Writer/authors would have more control over styling, links, media enclosures, etc., and readers would have more control over how and where they consume it. It’s decentralized social media, but without the need to peer through ActivityPub or anybody else’s API and squeeze our toothpaste through its tubes.</p>

<p data-omnivore-anchor-idx="24">Dave asked me to respond to his podcast, and while I thought about making an audio response, a blog post is more my metier.</p>

<p data-omnivore-anchor-idx="25">If this is going to work, I think there are at least four problems we’d have to solve:<br data-omnivore-anchor-idx="26">
</p><ul data-omnivore-anchor-idx="27"><li data-omnivore-anchor-idx="28">Everyday users need a <strong data-omnivore-anchor-idx="29">default writer and reader</strong>, preferably in the same place. It would be wonderful to be able to bring your own tools to bear and plug into the endpoints and have it just work. But nobody should need to fish around for that stuff. The defaults should be just opinionated enough (for instance, I like the Mastodon client Ivory, built on the ashes of TweetBot) that people feel like they’re getting a slick, finished UI and UX experience. That’s why people are gravitating to Threads: Meta knows how to put one together. But that’s not rebuilding the electrical grid from scratch. We know how to do that too.</li><br data-omnivore-anchor-idx="30">
<li data-omnivore-anchor-idx="31">We need <strong data-omnivore-anchor-idx="32">user and content discovery</strong>. We have to be able to find each other. And that’s what a lot of the heavy lifting of these other platforms is devoted to: to find people and things you didn’t know you were looking for. Again, this feels like a solvable problem.</li><br data-omnivore-anchor-idx="33">
<li data-omnivore-anchor-idx="34">We need <strong data-omnivore-anchor-idx="35">metrics</strong>. Most writers work for publishers, and publishers want to know whether their content is reaching people. It’s tempting to load this up with a lot of cruft, but impressions, clicks, reposts, quote posts, etc. is doable without a ton of advertising nonsense. Social media companies figured this out, but bloggers did too, a lot earlier.</li><br data-omnivore-anchor-idx="36">
<li data-omnivore-anchor-idx="37">We need <strong data-omnivore-anchor-idx="38">moderation</strong>. A wide-open social network becomes a highly abusive social network <em data-omnivore-anchor-idx="39">fast</em> in 2023. And nobody who isn’t a Nazi wants to hang out at a Nazi bar. So we need tools to block and flag and maybe even ban people who use the platform to spam each other, impersonate real people, and abuse other people on the platform. In the now-seminal “<a data-omnivore-anchor-idx="40" href="https://www.theverge.com/2022/10/28/23428132/elon-musk-twitter-acquisition-problems-speech-moderation">Welcome to Hell, Elon</a>,” Nilay Patel correctly identified content moderation as Twitter’s actual product: it’s what Twitter-the-company added to Twitter-the-protocol. We don’t necessarily need a Twitter-sized overhead, or a complex system of federated moderators, but it’s going to be a problem, so we’d need tools to address it.</li></ul>

<p data-omnivore-anchor-idx="41">But in terms of philosophy and vision, I’m all for it. RSS remains incredibly vital to what I do, and its potential as both a reading AND a writing platform remains untapped. You can write using your own tool and broadcast it everywhere. And Dave’s right: this worked for podcasts (the phrase “anywhere you get your podcasts!” is a great advertisement for interoperability breaking any single platform’s dominance), it worked for blogs, and it can work for this strange multimodal thing we’ve created called social media. It worked for the world wide web! And I will be ride or die for the open web until my life comes to an end.</p>

<p data-omnivore-anchor-idx="42">Now we just need to work together to make it happen. And I confess: my tools are limited here. I can’t (really) code, I can’t (really) design, I can’t build a moderation feature. I can evangelize, I can strategize, and I can write. But I can do those things (in all modesty) very, very well.</p>

<p data-omnivore-anchor-idx="43">So let’s do this thing. Why not? Twitter is dying, and Facebook is fading. None of the replacements have eaten their lunch yet. Why not make a swing for the open web? Why not <em data-omnivore-anchor-idx="44">try</em>? </p>










</div></DIV></DIV>