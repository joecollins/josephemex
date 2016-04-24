---
layout: post
title: Link all the things!
---
#Link Emails And Phone Numbers!
I see a lot of times where people don't link emails or phone numbers. I think this could be due to a lot of factors, including usability opinions, but I won't go into that. I just don't believe enough value is placed on providing clickable links to resources such as email addresses, so here's how!

##Phone Numbers
Phone numbers should definitely be links, this makes calling your company (or you) easier for mobile users and those using various browser extensions. It's a usability bonus and it's difficult to argue against. The syntax for this is simply as below, replace 123456 with your phone number:

~~~~
<a href="tel:123456">123456</a>
~~~~ 

##Email
This one gets a little friction because generally linking email addresses properly opens up an email client on click if there's one available. While this is true, this is desirable behaviour - if a user clicks on your email address, it's reasonable to believe they want to email you. The other possible downside is that this opens you up to spam, however modern email clients have such good spam protection that I don't consider this an issue.

The syntax is below, just replace "email@example.com" with your email.

~~~~
<a href="mailto:email@example.com">email@example.com</a>
~~~~

This can be easily extended (and mixed/matched) to prepoulate the subject, CC and BCC, or body text fields in your email client. These are added as a url query with the ? operator, with the syntax below:

~~~~
Add a subject (change "hello%20world"):
<a href="mailto:email@example.com?subject=hello%20world">email@example.com</a>

Add a CC (change "differentemail@example.com"):
<a href="mailto:email@example.com?cc=differentemail@example.com">email@example.com & differentemail@example.com</a>

Add a BCC (change "differentemail@example.com"):
<a href="mailto:email@example.com?bcc=differentemail@example.com">email@example.com & differentemail@example.com</a>

Add an email body (change "hello%20world"):
<a href="mailto:email@example.com?body=hello%20world">email@example.com</a>
~~~~

And these can be combined using the & operator:

~~~~
Add a subject and a body:
<a href="mailto:email@example.com?subject=hello%20world&body=goodbye%20world">email@example.com</a>
~~~~