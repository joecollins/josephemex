---
layout: post
title: SCSS (SASS) for developers (part one)
---
####Intro
SCSS (sometimes referred to as SASS) is a CSS preprocessor that allows for a lot of extended features. Unfortunately there aren't a lot of SCSS quick start guides for developers to quickly become well well introduced, so consider this that high-level syntax and concept guide. I'll assume you know CSS, and that your environment is fully installed.

The first thing you need to know is that your CSS file is already SCSS, due to the syntax being so similar and everything that exists in CSS being present in SCSS, so there's no overhead in converting to SCSS (although you might want to spend some time organising things to be a more Sassy-CSS way).

####Post index
You can learn about partials (including _underscore file naming)/imports here
You can learn about Mixins


####Partials
Partials are used to divide SCSS files into smaller, maintainable chunks. How you choose to divide your files is upto you, but on any project with more than a thousand lines this can save a lot of time. Typically division can be included

To add a partial simply make a new SCSS file, and then call it with the syntax:

~~~~
@import 'newFile';
~~~~

You do not need to include the .scss file extension. When you compile your SCSS this file will be imported in that spot as if it was built like a single giant file.

