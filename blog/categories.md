---
layout: blog
title: Category Overview
menu: menuBlog
topMenu: Blog
menuLink: index.html
---

{% for tag in site.categories %} 
  <h2 id="{{ tag[0] }}">{{ tag[0] | capitalize }}</h2>

  <ul class="post-list">
    {% assign pages_list = tag[1] %}  
    {% for post in pages_list %}
      {% if post.title != null %}
	{% if group == null or group == post.group %}
      <li><a href="{{ site.url }}{{ post.url }}">{{ post.date | date_to_string }} &raquo;{{ post.title }}</a></li>

      {% endif %}
     {% endif %}
    {% endfor %}
    {% assign pages_list = nil %}
  </ul>
{% endfor %}