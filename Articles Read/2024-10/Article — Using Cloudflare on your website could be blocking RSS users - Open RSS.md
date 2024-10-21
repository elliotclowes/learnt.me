---
id: a0307099-b0c6-4a0a-b828-ab2da6fabce5
site_name: openrss.org
date_published: 2024-10-16
date_saved: 2024-10-17
date_read: 2024-10-19
date_archived: 2024-10-19T17:36:18.000Z
original_url: https://openrss.org/blog/using-cloudflare-on-your-website-could-be-blocking-rss-users
omnivore_url: https://omnivore.app/me/using-cloudflare-on-your-website-could-be-blocking-rss-users-ope-19299b97b24
---

 - Site: openrss.org
 - By: 
 - Date published: 2024-10-16
 - Date read: [[2024-10-19]]
 - [Read Original](https://openrss.org/blog/using-cloudflare-on-your-website-could-be-blocking-rss-users)
 - [Read on Omnivore](https://omnivore.app/me/using-cloudflare-on-your-website-could-be-blocking-rss-users-ope-19299b97b24)
 - Tags:  #Cloudflare  #RSS  #Technology 
 - Notes: 

**Note:** Below is the text from the article, with any ==highlights== done by me. None of the writing below is by me.

# Article text
<DIV id="readability-content"><DIV data-omnivore-anchor-idx="1" class="page" id="readability-page-1"><article data-omnivore-anchor-idx="2">
                        
                        
                        <picture data-omnivore-anchor-idx="3">
<source data-omnivore-anchor-idx="4" srcset="https://proxy-prod.omnivore-image-cache.app/0x0,s7iKH0uR6XMTozqtBLYGm0j8XlyZrk6psC7TM79heJVY/https://openrss.org/media/cloudflare-headline-image-dark.png," media="(prefers-color-scheme: dark)">
<img data-omnivore-anchor-idx="5" data-omnivore-original-src="https://openrss.org/media/cloudflare-headline-image.png" src="https://proxy-prod.omnivore-image-cache.app/0x0,s4zNS0hPz6vwhAK1Eg16NIn_lTr5Ef-3gCnAgpLYWSuM/https://openrss.org/media/cloudflare-headline-image.png" alt="Image of Cloudflare logo of what looks like a sun setting on a horizon with the words Cloudflare underneath in a super bold, dark gray font">
</picture>

<p data-omnivore-anchor-idx="6">Many users prefer to use an RSS feed reader to stay up to date with the content on the websites they visit. But if you've enabled Cloudflare on your website, you're likely blocking these RSS users from accessing your website content without realizing it.</p>
<a data-omnivore-anchor-idx="7" id="the-cloudflare-features-that-block-rss-readers" href="#the-cloudflare-features-that-block-rss-readers"></a>
<p data-omnivore-anchor-idx="8">In Cloudflare's dashboard, you'll find <a data-omnivore-anchor-idx="9" href="https://developers.cloudflare.com/waf/tools/">tools</a> designed to block bot traffic to your website. Particularly, the Bot Fight Mode and block all "AI scrapers and crawlers" options below. When enabled, these features end up blocking users who access your website through RSS readers, even though RSS readers are legitimate and aren't malicious bots.</p>
<figure data-omnivore-anchor-idx="10">
<img data-omnivore-anchor-idx="11" data-omnivore-original-src="https://openrss.org/media/cloudflare-bot-security-dashboard-detection-configuration.png" src="https://proxy-prod.omnivore-image-cache.app/0x0,sdassCNxa2-co61ng8B7b4ExYpKtQGqyKoCiOf8T6wrw/https://openrss.org/media/cloudflare-bot-security-dashboard-detection-configuration.png" alt="An image of the Bot Fight Mode and AI Scrapers and Crawlers configuration toggles on Cloudflare's Security dashboard">
<figcaption data-omnivore-anchor-idx="12">A screenshot of Cloudflare's Bot Fight Mode and block all "AI scrapers and crawlers" features that block RSS readers from accessing a website</figcaption>
</figure>

<a data-omnivore-anchor-idx="13" id="how-cloudflare-blocks-rss-readers-from-your-website" href="#how-cloudflare-blocks-rss-readers-from-your-website"></a>
<p data-omnivore-anchor-idx="14">When enabling the tools, Cloudflare will evaluate each visit to your website and determine whether the visit is from an AI scraper or "bot" based on a <a data-omnivore-anchor-idx="15" href="https://developers.cloudflare.com/bots/concepts/bot-score">score</a> , which ironically Cloudflare uses AI to generate.</p>
<picture data-omnivore-anchor-idx="16">
<source data-omnivore-anchor-idx="17" srcset="https://proxy-prod.omnivore-image-cache.app/0x0,sL15vlQ3S56oSgzsuLBXQu-HeOahX-Ovwc8ghRKjKE68/https://openrss.org/media/rss-readers-blocked-by-cloudflare-dark.png," media="(prefers-color-scheme: dark)">
<img data-omnivore-anchor-idx="18" data-omnivore-original-src="https://openrss.org/media/rss-readers-blocked-by-cloudflare.png" src="https://proxy-prod.omnivore-image-cache.app/0x0,slIAXB0qEHYuSdlkhmfEQzipeJOHxXMBU5jMf2C3IzFg/https://openrss.org/media/rss-readers-blocked-by-cloudflare.png" alt="Image of an RSS reader blocked by Cloudflare">
</picture>

<p data-omnivore-anchor-idx="19">Then, when a user's RSS reader attempts to read your website, Cloudflare presents it with a number of <a data-omnivore-anchor-idx="20" href="https://developers.cloudflare.com/waf/reference/cloudflare-challenges/">challenges</a> that the reader would never be able to fulfill.</p>
<p data-omnivore-anchor-idx="21">Here's an example of the Human Verification challenge that an RSS reader would be shown when it tries to visit your website. The challenge requires a human to solve and, because an RSS reader is not a human, it can never complete them.</p>
<picture data-omnivore-anchor-idx="22">
<source data-omnivore-anchor-idx="23" srcset="https://proxy-prod.omnivore-image-cache.app/0x0,sGMEzQ_AccKrYxS7lu8pB9ZdKCGwx_nKty_rQGuM_CzU/https://openrss.org/media/cloudflare-human-verification-dark.png," media="(prefers-color-scheme: dark)">
<img data-omnivore-anchor-idx="24" data-omnivore-original-src="https://openrss.org/media/cloudflare-human-verification.png" src="https://proxy-prod.omnivore-image-cache.app/0x0,sSTIFL6QeuahZ4W6uWBHecYOHj0G3vGJ_gQmIiATC-Ls/https://openrss.org/media/cloudflare-human-verification.png" alt="A screenshot of Cloudflare-enabled website presenting a human verification screen">
</picture>

<p data-omnivore-anchor-idx="25">In other cases, Cloudflare will simply block the RSS reader from accessing your website without a reason.</p>
<img data-omnivore-anchor-idx="26" data-omnivore-original-src="https://openrss.org/media/cloudflare-block.png" src="https://proxy-prod.omnivore-image-cache.app/0x0,sSLJBEy2OhmAN8bVBKxan5tSmtPf-J_0XYSs8r_tRhvw/https://openrss.org/media/cloudflare-block.png" alt="A screenshot of Cloudflare-enabled website presenting a human verification screen">

<p data-omnivore-anchor-idx="27">The only way to resolve when Cloudflare blocks an RSS reader from accessing your website is by contacting you directly and asking you to make a custom rule to unblock it. But Cloudflare shouldn't expect people to contact every owner of every Cloudflare website that blocks their RSS reader. And you shouldn't have to waste time logging into Cloudflare to add an exception every time they block an RSS reader, either.</p>
<a data-omnivore-anchor-idx="28" id="unblock-rss-readers-while-still-using-cloudflare" href="#unblock-rss-readers-while-still-using-cloudflare"></a>
<p data-omnivore-anchor-idx="29">Even though Cloudflare blocks RSS readers from your website, you can whitelist RSS readers as a workaround. This would at least unblock RSS readers without having to turn off any security features that you may have already been enabled until Cloudflare better addresses the issue.</p>
<p data-omnivore-anchor-idx="30">First, find the user agent of any blocked RSS reader in Cloudflare's analytics dashboard. The&nbsp;<code data-omnivore-anchor-idx="31" class="hljs language-dockerfile language-ebnf"><span data-omnivore-anchor-idx="32" class="hljs-keyword">User</span>-Agent</code>&nbsp;of most good RSS readers usually include the name of the reader, it's URL, or a word like "RSS" or "feed" that makes it obvious that it's an RSS reader.</p>
<p data-omnivore-anchor-idx="33">Once you've identified an RSS reader's user agent, you can&nbsp;<a data-omnivore-anchor-idx="34" href="https://developers.cloudflare.com/waf/custom-rules/use-cases/allow-traffic-from-ips-in-allowlist/">create a custom</a>&nbsp;rule that explicitly whitelists and allows all traffic by the reader's IP address or by it's user agent string. Note that user agents can be disguised, so it's often better to whitelist the reader's IP address instead of the user agent. If you'd like to whitelist Open RSS, please&nbsp;<a data-omnivore-anchor-idx="35" href="https://openrss.org/contact">contact us</a>&nbsp;for the required information.</p>
<a data-omnivore-anchor-idx="36" id="cloudflare-needs-a-better-way-to-allow-rss-readers" href="#cloudflare-needs-a-better-way-to-allow-rss-readers"></a>
<p data-omnivore-anchor-idx="37">Cloudflare offers a bot verification program to which RSS readers owners can manually apply to avoid being blocked by websites, but this program isn't guaranteed to work and it suffers from quite a few problems.</p>
<ul data-omnivore-anchor-idx="38">
<li data-omnivore-anchor-idx="39"><p data-omnivore-anchor-idx="40"><strong data-omnivore-anchor-idx="41">The verification process is flimsy</strong> — They're using a <a data-omnivore-anchor-idx="42" href="https://docs.google.com/forms/d/e/1FAIpQLSdqYNuULEypMnp4i5pROSc-uP6x65Xub9svD27mb8JChA_-XA/viewform">Google form</a> for applications to the program. Then after applying, no notification is sent that they're working on it or even received the application successfully (we've tried <a data-omnivore-anchor-idx="43" href="https://openrss.org/issue/144#202406210145">applying twice</a>), with no progress updates or expected timeframe for completion.</p>
</li>
<li data-omnivore-anchor-idx="44"><p data-omnivore-anchor-idx="45"><strong data-omnivore-anchor-idx="46">Verified RSS readers are still being blocked</strong> — There are reports that RSS readers Cloudflare has verified as "good bots" are still being blocked from websites. If Cloudflare has successfully approved an RSS reader as a "good bot", it shouldn't be blocked or still require website owners to add any custom exception rules.</p>
</li>
<li data-omnivore-anchor-idx="47"><p data-omnivore-anchor-idx="48"><strong data-omnivore-anchor-idx="49">Unblocking RSS readers across multiple websites is cumbersome</strong> — Cloudflare's only resolution to unblocking RSS readers is for the owners of the readers to contact each website owner directly and ask for an exception to be made. While that may work for one-off cases, this is unreasonable for RSS readers that have to access thousands of different Cloudflare-enabled websites each day. It's also overwhelming for website owners to configure exceptions for each and every RSS reader.</p>
</li>
</ul>
<p data-omnivore-anchor-idx="50">To be clear, there's nothing wrong with using Cloudflare's security tools on your website to help deal with malicious AI bots, scrapers, and potential attacks. But Cloudflare needs to ensure that people who use RSS tools aren't blocked from accessing your website content, and make it easier to resolve when they are.</p>
 
    <small data-omnivore-anchor-idx="51">
        <br data-omnivore-anchor-idx="52">
        <center data-omnivore-anchor-idx="53">❤</center>
        <em data-omnivore-anchor-idx="54">
            Open RSS is a registered 501(c)(3) nonprofit headquartered in the
            District of Columbia, USA and funded only by voluntary donations of
            its users. If you enjoy using Open RSS, we'd be so grateful if you'd
            consider
            <a data-omnivore-anchor-idx="55" href="https://openrss.org/donate">donating</a> to help us grow and
            continue to provide you with a quality and reliable service.
        </em>
    </small>

                    </article></DIV></DIV>