---
layout: post
title: Building a simple archive page with Jekyll
---
#An Archive Page With Jekyll
An archive page is a single page of a blog that displays all (or some) of your posts, usually in chronological order, so that visitors can quickly navigate your blog. This was actually very simple to implement, simply create a new page (next to your index.html), that included a snippet something like this:

~~~~
---
layout: default
---

{% raw %}
{% for post in site.posts %}          
  <a href="{{ post.url | prepend: site.baseurl }}"><h3><strong>{{ post.title }}</strong></h3></a>
  <p>{{ post.content | truncate: 250}}</p>
{% endfor %}
{% endraw %}
~~~~

This basically loops through all of your posts, displays the title (and makes the title a link and H3), then posts the first 250 characters of the post. The preview is removed by deleting the p and it's contents, if you wish.

This could be extended to being a "most recent 5 posts" (or however many), by simply adding a limit to the for loop, like so (remember to specify your site layout at the top like before):

~~~~
{% raw %}
{% for post in site.posts limit:5 %}          
  <a href="{{ post.url | prepend: site.baseurl }}"><h3><strong>{{ post.title }}</strong></h3></a>
  <p>{{ post.content | truncate: 250}}</p>
{% endfor %}
{% endraw %}
~~~~

You could add divs, or lists to this however you wish, infact the main page of my blog uses a list like so:

~~~~
{% raw %}
<ul>
  {% for post in site.posts limit:5 %}
  <li>
    <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
  </li>
  {% endfor %}
</ul>
{% endraw %}
~~~~