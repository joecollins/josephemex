---
layout: post
title: Verbose CSS Selectors
---
#Really Long CSS Selectors
This exercise came to me while I was working with some awkward CSS selectors that are a little non standard and wondered what the most obscene CSS selector for a single div could be. This isn't an exercise in usability or practicality, though the end result should work fine in practise please don't use it.

The HTML for this will be very simply:

~~~~
<html>
  <body>
    <div class="not-target"></div>
    <div class="target"></div>
    <div class="not-target"></div>
    <div class="not-target  target"></div>
  </body>
</html>
~~~~

And then I need to make everything visible so I can tell that things are happening (give everything a width, height and border so I know it's all displaying and that I'm styling only the right one), eg:

~~~~
.not-target, .target {
  width: 50px;
  height: 50px;
  display: block;
  border: 1px solid #FF0000;
}
~~~~

And now it's time to begin to select the target, starting with the obvious (and flawed) - most people would/should stop here and just write better markup:

~~~~
.target {
  background: black;
}
~~~~

This is pretty simple though, so I'll add a quick "not" selector to get rid of the .not-target I'm selecting here:

~~~~
.target:not(.not-target) {
  background: black;
}
~~~~

Now I'm gonna get silly with it, because this does the task in this situation:

~~~~
.target:nth-of-type(even):not(.not-target) {
  background: black;
}
~~~~

Obviously to scale it I could do this:

~~~~
.target:nth-of-type(even):not(.not-target), .target:nth-of-type(odd):not(.not-target) {
  background: black;
}
~~~~

This is, in practise, flawless - but not as over the top as I think I can do, so I'll add a parent (in this case the parent is the "body" element):

~~~~
body > .target:nth-of-type(even):not(.not-target)
~~~~

And since I have a not-target preceding my target, this works:

~~~~
body > .not-target ~ .target:nth-of-type(even):not(.not-target)
~~~~

Other things I know is that this is not an input of any kind, and doesn't have a target:

~~~~
body > .not-target ~ .target:nth-of-type(even):not(.not-target):not([type="*"]):not([target])
~~~~

This is around the point when progression is an endless string of :not()s, maybe some obscure css hacks could make this even weirder in the future.

##Changes
Some changes I could have made would be to use the * selector instead of naming "body" and ".not-target", though that would have been less readable, at this stage does readability matter?

##Conclusion
The end result is this:

~~~~
body > .not-target ~ .target:nth-of-type(even):not(.not-target):not([type="*"]):not([target]), body > .not-target ~ .target:nth-of-type(odd):not(.not-target):not([type="*"]):not([target]) {
  background: black;
}
~~~~

And if we write this in "english", it translates to:

~~~~
Select children of the body element that are preceded by not-target, that are either an even or odd iteration of the .target class. The selection cannot be the .not-target class, that doesn't have a type, and isn't a target.
~~~~