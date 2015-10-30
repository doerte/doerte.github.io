---
layout: blog
title: Blog Archive
menu: menuBlog
---

{% for post in site.posts %}
  <div class="post">
    <h3>{{ post.date | date_to_string }} &raquo; <a href="{{ post.url }}">{{ post.title }}</a></h3>
	</div>
{% endfor %}