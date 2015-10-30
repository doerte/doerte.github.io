---
layout: blog
title: Blog
menu: menuBlog
---

<p><div align="right">Get my Blog-posts as a feed <a href="/atom.xml"><img alt="Get my feed" 
src="/img/rss-icon.png"></a></div></p>



{% for post in site.posts limit:10 %}
  <div class="post">
    <h2>{{ post.date | date_to_string }} &raquo; <a href="{{ post.url }}">{{ post.title }}</a></h2>
    <p class="excerpt">
    {{ post.content | strip_html | truncatewords: 200 }} &nbsp;
    {% capture postdiff %} {{post.content | number_of_words | minus:200}} {% endcapture %}
    {% unless postdiff contains '-' %}
      <a href="{{ post.url }}" class="read-more">read more</a>
    {% endunless %}
	  </p>
      </div>
{% endfor %}


---------
On this site only the ten most recent posts are displayed. To see an overview of all posts, please visit the [archive](/blog/archive)!