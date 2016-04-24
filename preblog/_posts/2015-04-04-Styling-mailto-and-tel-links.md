---
layout: post
title: Styling mailto and tel links
---
#Styling MailTo and Tel Links
A lesser known feature of CSS is that mailto and tel links can be specifically styled which allows for much more accessible, interactive or interesting designs. One use for this could be to give different colours to emails and phone numbers, without having to assign an additional class each time. To do this, we'll be using the attribute selector. Any regular styling will work, but I'll be mostly changing the text colour to red, just so we can see things are happening.

##Starting out
Starting out, styling every mailto or tel link is very easy, and can be done with this CSS:

~~~~
a[href^="tel"] {
  color: red;
}
a[href^="mailto:"] {
  color: green;
}
~~~~

This will turn ANY link that uses "tel:" red, and any "mailto" link will become green.

This can be extended to style specific links to become different colours, eg support could be green and sales could be orange. This uses a slightly different selector, a "wildcard" attribute selector rather than a specific "begins with" attribute selector.

HTML:

~~~~
<a href="mailto:support@example.com">
  Email support
</a>
<br />
<a href="mailto:sales@example.com">
  Email sales
</a>
~~~~

CSS:

~~~~
a[href*="support@example.com"]
{
  color: red;
}
a[href*="sales@example.com"]
{
  color: orange;
}
~~~~

This is just a case of using *= instead of ^=

This can be extended to be more advanced and a bit easier by using pre-filled email mailtos, and then colouring the links based on the content of the emails. In the example below we have an email link which set the subject to "hello world" and the body to "goodbye world". The space for this must be "%20". This will be style to colour any emails with the subject as "hello world" to be red, and any emails with the body as "goodbye world" to be underlined. 

In this case these two selectors will make our single link red and underlined as a demonstration of both.

HTML:

~~~~
<a href="mailto:email@example.com?subject=hello%20world&body=goodbye%20world">
  Email example, subject is "hello world" and body is "goodbye world".
</a>
~~~~

CSS:

~~~~
a[href*="subject=hello%20world"]
{
  color: red;
}
a[href*="body=goodbye%20world"]
{
  text-decoration: underline;
}
~~~~