---
layout: post
title: CSS Filters
---
####Intro
CSS Filters aren't very well known (mostly due to poor support), but the gist of it is that they apply an effect to an element. They can be used for a few different effects, I'm going to start with what I thought was the most interesting: video.

####Basic syntax
There are a lot of different CSS filters, but the basic syntax is:

~~~~
  filter: function(parameter);
~~~~

Browsers have a number of filter functions built in, the working example below will use sepia:

~~~~
  -webkit-filter: sepia(100%);
  filter: sepia(100%);
~~~~

As you can see, browser prefixes are required for webkit.

####How they work
CSS Filters work by applying the filter on top of the element you've selected, which is really simple. This is often applied to a background image so that it doesn't take focus, but you apply it to other elements for interesting effects

####YouTube Videos
To apply a filter to a YouTube video, you can either wrap everything in a div or simply target the iframe the video is in.

HTML:

~~~~
<iframe width="560" height="315" src="https://www.youtube.com/embed/0vrdgDdPApQ" frameborder="0" allowfullscreen></iframe>
~~~~

CSS:

~~~~
iframe {
  -webkit-filter: sepia(100%);
  filter: sepia(100%);
}
~~~~

This makes the video sepia, with the side effect of making the player sepia as well. Some effects won't be noticeable on the video player, such as a slight blur or maybe some saturation

####Lighten and Darken SCSS alternatives
Native CSS Filters can replace the lighten() and darken() functions from SCSS, by 