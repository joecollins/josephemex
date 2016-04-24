---
layout: post
title: CSS Scientific Notation
---
#Scientific Notation in CSS
In CSS a lesser known feature is that there are datatypes like a "real" programming or scripting language, which includes a number datatype. Part of this number datatype is that you can use proper scientific notation in your CSS. This is pretty useless as far as I can tell, unless you want to legibly put a very large number in your CSS (eg, if you want a 100,000px wide object it might be easier to just write 10e4);

##Usage
Any CSS number can be used with px, %, VH, calc, etc. This includes scientific notation An example of this is:

~~~~
div {
  height: 10e1px;
}
~~~~

Which sets the height of all divs to 100px (10X10)

You could also use this with calc, if you wanted to:

~~~~
div {
  height: calc(10e2px - 10e1px);
}
~~~~

Which sets the height of all divs to 900. This looks pretty overengineered for everyday use, but for ridiculous large value fringe cases (which are rare), this could be useful. It could also be useful for high-precision shapes.

Overall, it's a neat feature and could be useful in hacks and weird CSS playgrounds, but probably shouldn't be used in production for 90% of the time.