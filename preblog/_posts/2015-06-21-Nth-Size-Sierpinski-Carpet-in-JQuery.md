---
layout: post
title: Nth-Size Sierpinski Carpet in JQuery
---
#JQuery Sierpinski Carpet
I made a Sierpinski Carpet ([Wiki link](https://en.wikipedia.org/wiki/Sierpinski_carpet)) in JQuery that accepts an unlimited number of levels (eg, it could go build Sierpinski Carpet level 1000 if your computer and browser can handle it). If you want to skip the "how" then you can go ahead and see it at [http://joseph.mx/sierpinski](http://joseph.mx/sierpinski) or view the code at [codepen](http://codepen.io/anon/pen/MwEPxB)

##The quirk
When I originally began this I started writing as if every level is equal (since they're all very similar) which lead to a lot of road blocks. To get around this I decided to manually write out each level to properly understand how it works, this went something like this:

* Level One - This level takes a single square and then divides it into 9 squares (or overlays 9 squares), and then deletes (hides) the 5th square. Squares are named 1-9.
* Level Two - This level adds 9 squares into every level one square, except for square 5. These level 2 squares are also named 1-9 (so there are 9 "level2 square1" elements). Level2 square 5 is hidden
* Level Three - This is almost identical to level two, so I moved onto my next (and final approach)

I realised that everything except for the first level (going from 1 to 9 squares) could happen with the same script, allowing for "Nth" number of levels so long as level one runs first and seperately.

##Execution
So to execute on this the flow is:

* Clear the "outer" element (so that we can run multiple times)
* Run the level one function (which places 9 squares, each of which is 1/3rd the size of the outer element, so they tile. Paint the 5th square black so it's "hidden"). The naming convention for squares are "levelX squareY"
* Run the level two function (which places 9 squares in each level1 square, 81 total, and makes the 5th square black)

The level two function is then reran, just replace 9 squares in each level 1 square, with 9 squares in every previous levels squares.

##Performance
I think with some work I could make this run a bit faster, but the nature of exponentials means that this runs very very slowly (for me it starts getting noticeably laggy at level 4, but this is machine dependant, obviously). This makes this a good illustration for how a lot of DOM elements quickly slow down pages.