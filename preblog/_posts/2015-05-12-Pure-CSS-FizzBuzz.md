---
layout: post
title: Pure CSS FizzBuzz
---
#Pure CSS FizzBuzz
Following a recent blog post about a designer struggling with FizzBuzz due to not using JavaScript much, I decided to rework the problem in pure CSS to see how possible that is.

It turned out to be pretty straight forward to do in a bastardised implementation, which I did by changing the rules slightly:

Divs are produced by JQuery (could be pure JS, but I made this easier on myself) so that using a variable is possible, manually inserting divs could also be done

Colours instead of numbers and words can be done - I chose black for a number, green for multiples of 3, blue for multiple of 5 and orange for multiple of 3 AND 5

To skip to my codepen, click [here](http://codepen.io/anon/pen/xGVKgm)

##The setup
The initial set up is easy:

Markup:

~~~~
<div class="container">

</div>
~~~~

JQuery (change the limit of the for to change the number to count to):

~~~~
for(i = 0; i < 15; i++){
  $(".container").append("<div class='fizzbuzz'></div>")
}
~~~~

##The CSS
The CSS section is where everything happens, I make the boxes somewhat bearable by styling the fizzbuzs class:

~~~~
.fizzbuzz {
  width: 50px;
  height: 50px;
  background: black;
  margin: 20px;
  float: left;
  color: white;
  text-align: center;
}
~~~~

I then go on to determine that divisble by 3 is green, divisible by 5 is blue and divisible by 3 and 5 is orange (fizz/buzz/fizzbuzz)

~~~~
.fizzbuzz:nth-of-type(3n){
  background: green;
}

.fizzbuzz:nth-of-type(5n){
  background: blue;
}

.fizzbuzz:nth-of-type(3n).fizzbuzz:nth-of-type(5n){
  background: orange !important;
}
~~~~

I then added some words using content and ::before to make things more readable

~~~~
.fizzbuzz:nth-of-type(3n)::before{
  content: "fizz";
}

.fizzbuzz:nth-of-type(5n)::before{
  content: "buzz";
}

.fizzbuzz:nth-of-type(3n).fizzbuzz:nth-of-type(5n)::before{
  content: "fizzbuzz"
}
~~~~

The numbers stumped me and I'm not sure on how to proceed, but this could feasibly be pure CSS if the jquery was replaced with manual copy/pasting.

The full CSS file is:

~~~~
.fizzbuzz {
  width: 50px;
  height: 50px;
  background: black;
  margin: 20px;
  float: left;
  color: white;
  text-align: center;
}

.fizzbuzz:nth-of-type(3n){
  background: green;
}
.fizzbuzz:nth-of-type(3n)::before{
  content: "fizz";
}

.fizzbuzz:nth-of-type(5n){
  background: blue;
}
.fizzbuzz:nth-of-type(5n)::before{
  content: "buzz";
}

.fizzbuzz:nth-of-type(3n).fizzbuzz:nth-of-type(5n){
  background: orange !important;
}
.fizzbuzz:nth-of-type(3n).fizzbuzz:nth-of-type(5n)::before{
  content: "fizzbuzz"
}
~~~~