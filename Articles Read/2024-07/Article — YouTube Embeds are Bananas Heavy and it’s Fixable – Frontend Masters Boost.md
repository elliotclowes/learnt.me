---
id: b00ad7cf-353d-4cea-b715-710feec538c7
site_name: frontendmasters.com
author: Chris Coyier CodePen
date_published: 2024-07-01
date_saved: 2024-07-09
date_read: 2024-07-09
date_archived: 2024-07-09T20:22:04.000Z
original_url: https://frontendmasters.com/blog/youtube-embeds-are-bananas-heavy-and-its-fixable/
omnivore_url: https://omnivore.app/me/you-tube-embeds-are-bananas-heavy-and-it-s-fixable-frontend-mast-1909740170e
---

 - Site: frontendmasters.com
 - By: Chris Coyier CodePen
 - Date published: 2024-07-01
 - Date read: [[2024-07-09]]
 - [Read Original](https://frontendmasters.com/blog/youtube-embeds-are-bananas-heavy-and-its-fixable/)
 - [Read on Omnivore](https://omnivore.app/me/you-tube-embeds-are-bananas-heavy-and-it-s-fixable-frontend-mast-1909740170e)
 - Tags:  #Technology  #The_Web  #YouTube 
 - Notes: 

**Note:** Below is the text from the article, with any ==highlights== done by me. None of the writing below is by me.

# Article text
TL;DR: YouTube Embeds are like 1.3MB in size with no shared resources between multiple embeds. Using a [<lite-youtube>](https://github.com/paulirish/lite-youtube-embed) Web Component is more like 100k, _does_ share resources, and sacrifices no functionality. 

You can put a YouTube video on any website. They help you do it. Under the **Share** menu right on youtube.com there is an option to **<> Embed** and you’ll see bit of HTML with an `<iframe>` in it. 

![[ac4c9158794627ec3f8473f568ba760e.jpg]]

<iframe>s are never wonderful for performance, but they make sense for protected third-party content.

This is what I’m getting as I write:

`<iframe 
  width="560" 
  height="315" 
  src="https://www.youtube.com/embed/LN1TQm942_U?si=EfW_M4bEHEO-idL3"
  title="YouTube video player"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
  referrerpolicy="strict-origin-when-cross-origin"
  allowfullscreen>
</iframe>`Code language: HTML, XML (xml)

If I were Team YouTube, I’d get `loading="lazy"` on there to help with performance right away. No need for videos that aren’t even visible on the page to load right away. 

`<iframe 
  ...
  loading="lazy"
  >
</iframe>
`Code language: HTML, XML (xml)

Plus I’d put some inline styles on there to keep the video fluid and maintain the original aspect ratio. Or you could target these and do that yourself in CSS. Here’s assuming the videos are the standard 16 / 9 aspect ratio:

`iframe[src^="https://www.youtube.com/embed/"] {
  inline-size: 100%;
  block-size: auto;
  aspect-ratio: 16 / 9;
}`Code language: CSS (css)

But… let’s not keep this HTML at all. I’m sure you read this blog post title, but let’s put a point on it:

![[c1111d6db978e41e9413b1ad85e17318.jpg]]

On a page with literally _nothing at all on it_ other than a YouTube Embed, we’re looking at:

* 32 requests
* 1.3 MB of data transfer
* 2.76s to load the page on my current WiFi connection

[Zach Leatherman, equally exasperated by this](https://www.zachleat.com/web/youtube-embeds/), noted:

> The weight also grows linearly with every embed—resources are _not_ shared: two embeds weigh 2.4 MB; three embeds weigh 3.6 MB (you get the idea).

Wow.

Looks like sizes are up a bit since Zach last looked as well.

## The Appearance & Functionality

This is what you get from a YouTube Embed:

* You see a “poster” image of the video
* You see the title of the video
* You see a big play button — click it to play the video

This is very little UI and functionality, which is fine! We can absolutely do all this without this many resources.

## Why is it this way? 🤷‍♀️

I don’t think we have any good answers here. In fact, I heard from a little birdie who ran it up the pole that they have tested lighter embeds and _found them to reduce engagement_. 😭

I’m just gonna straight up say I don’t believe it. It’s like when Google told us that taking up half the screen with AI generated answers led to people clicking on third-party results _more_, but then refused to show data or allow us to track those clicks ourselves.

And hey — sometimes there are unexpected results in testing. That’s why we test instead of guess. But because this is _so_ counterintuitive and offtrack for so many other similar performance testing situations, this bears deeper scrutiny. It would benefit from an opening of the methodology and data. 

Like if you tell me that if you hit people with a stick and they smile more, I’m gonna want you to stop until we can look at what’s going on there.

I _really_ wish I could find a good link for this, but there is a famous story from YouTube engineers way-back-when who made a much lighter video page and put it into testing. They found, quite counterintuitively, that average page load times went _up._ But with a deeper look, they found that the lighter page was able to _reach more people, including people on low-power low-internet-speed devices_ who were able to actually use YouTube for the first time, and them using it much more slowed those averages. That’s awesome! The speed of using the site was up _relatively_ for everyone. The metric of the average page load speed was a red herring and ultimately not meaningful.

How do we know that’s not the same kind of thing happening here?

Remember the implications of all these resources isn’t just a little inconvenience. YouTube is so enormous we’re talking incredible amounts of wasted electricity and thus carbon output. Pulling a megabyte of data off every single YouTube Embed would be an incredible win all around. I might even say _not_ improving this is environmentally negligent.

## The Solution is to Replicate the Embed Experience Another Way. There are Open Source Web Components That Do It Well.

With a little dab of irony, Google’s own performance champion Paul Irish has had a web component doing just this for years and years and years:

[lite-youtube-embed](https://github.com/paulirish/lite-youtube-embed)

The pitch is solid:

> Provide videos with a supercharged focus on visual performance. This custom element renders just like the real thing but approximately 224× faster.

**Two hundred and twenty four** times faster. Which of course involves much less data transfer.

And I’d like to be very clear, also does the exact same thing as the default embed:

* You see a “poster” image of the video
* You see the title of the video
* You see a big play button — click it to play the video

You lose nothing and gain tons of speed, efficiency, and default privacy.

## Using Lite YouTube Embed

1. Link up the JavaScript to instantiate the Web Component
2. Use it

You could install it from npm or copy and paste a copy into your own project or whatever. Or link it from a CDN:

`import "https://esm.sh/lite-youtube-embed";`Code language: JavaScript (javascript)

That’s like this:

But the best way to use it is right in the README:

> Use this as your HTML, load the script asynchronously, and let the JS progressively enhance it.

`<script defer src="https://cdnjs.cloudflare.com/ajax/libs/lite-youtube-embed/0.3.2/lite-yt-embed.js"></script>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/lite-youtube-embed/0.3.2/lite-yt-embed.css" integrity="sha512-utq8YFW0J2abvPCECXM0zfICnIVpbEpW4lI5gl01cdJu+Ct3W6GQMszVITXMtBLJunnaTp6bbzk5pheKX2XuXQ==" crossorigin="anonymous" referrerpolicy="no-referrer" />

<lite-youtube videoid="ogfYd705cRs" style="background-image: url('https://i.ytimg.com/vi/ogfYd705cRs/hqdefault.jpg');">
  <a href="https://youtube.com/watch?v=ogfYd705cRs" class="lty-playbtn" title="Play Video">
    <span class="lyt-visually-hidden">Play Video: Keynote (Google I/O '18)</span>
  </a>
</lite-youtube>`Code language: HTML, XML (xml)

With async loaded JavaScript, note the `background-image` is put into the HTML so it can all look right before the JavaScript loads. 

## Alternatives

* [Shadow DOM version](https://github.com/justinribeiro/lite-youtube) (more protected styling, more annoying to style)
* Do it yourself  
   * Raymond Camden: [Building a YouTube Embed Web Component (both vanilla and WebC flavored)](https://www.raymondcamden.com/2022/11/17/building-a-youtube-embed-web-component-both-vanilla-and-webc-flavored)  
   * Adrian Roselli: [YouTube and Vimeo Web Component](https://adrianroselli.com/2024/06/youtube-and-vimeo-web-component.html)
* Mux: `<youtube-video>` (matches `<video>` DOM APIs)
* [React Port](https://github.com/ibrahimcesar/react-lite-youtube-embed) & [Next.js Official Version](https://github.com/vercel/next.js/tree/canary/packages/third-parties#youtube-embed)

### Learn to Work with Web Components

[ ![Frontend Masters logo](https://proxy-prod.omnivore-image-cache.app/0x0,sU83mBDc8OoN0ihG1vsfm8kAIqk4r9kQcm9Wy6YgH5ck/https://frontendmasters.com/blog/wp-content/themes/fem/images/course-shoutouts/generic.png) ](https://frontendmasters.com/courses/web-components/?utm%5Fsource=boost&utm%5Fmedium=blog&utm%5Fcampaign=youtube-embeds-are-bananas-heavy-and-its-fixable?utm%5Fsource=boost&utm%5Fmedium=blog&utm%5Fcampaign=youtube-embeds-are-bananas-heavy-and-its-fixable)

