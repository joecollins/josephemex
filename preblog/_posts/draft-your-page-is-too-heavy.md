---
layout: post
title: Your page is too heavy
---
####The Trend
Disclaimer: Since writing and publishing this post, I've found the tone doesn't reflect my intentions, but I don't think rewriting or deleting this post would be honest, so I'm keeping this post active and I'm truly sorry if you find this abrasive.

The current trend for landing pages, and most "design-first" websites, is using an unreasonable amount of assets. A lot of JS/Jquery libraries, a lot of fonts, a lot of hi-res images. The list goes on but so many companies are choosing to ignore how hostile this practice is. Obviously you're going to think your website is valuable, and it might be to a lot of people, but the problem isn't making people care about your content. The problem is making me sit still long enough on a busy day that I'll wait for your site to load just to find out what you do. Do I want to sit still for 10 seconds just to find out you're not relevant to me? Obviously not, so I need to know what you do before I can stop caring, and having me sit waiting for your site to download isn't going to help me transition from indifferent to caring. 

####How much stuff is too much?
Take the UK as an example, according to the [IBTimes](http://www.ibtimes.co.uk/broadband-internet-global-average-connection-speed-passes-4mbps-first-time-1469297) the average speed is 4.6Mbps (half a megabyte per second - files are usually measured in bytes, so I'll use this from now on). This means that 4MB background image you like will cost the user about 8 seconds - which for just an image is ridiculous. 

On a less extreme scale, if you have 1MB of JavaScript, 0.5MB of CSS and 2MB across images, your website is already at 3.5MB - or 7 seconds to load (ignoring having X amount of requests etc). How many users are waiting 7 seconds just to find out if you're what they're looking for? 

####Dealing with this
I can't dictate how other people run their website (which is good, not a complaint!), but I can run my website as an example of the way I hope the web evolves to. My design (which I bought as a psd and then turned it into this website) isn't horrendous (though isn't perfect), gets the message across and then allows users to go about their day or read on if I'm relevant - and this took up 210KB, about half a second to fully load. 

My website isn't relevant to most people, but that's fine, because I'm not holding users hostage for very long for them to find out that I'm not what they need. You wouldn't wait 7 seconds for this article, so please don't make me wait 7 seconds for your article.

Even without modifying your design at all you can probably reduce the amount of data you send by taking out anything that's not in use. Nobody will suffer if you only include font weights in use, or JS libraries that are useful to the experience. If you can't reduce the number of files, what about the compression? I just threw mod_pagespeed on my website, so I'm not much of an expert, but it alone helped a lot in compressing my assets.

####The limit
I came across a little extreme so far, so I want to mention that there is a limit - if your site legitimately relies on those assets, keep them. Web apps inherently need a lot of JS and photography blogs obviously need a lot of hires photography - but we're not all running web apps or photography blogs and need to remember that.