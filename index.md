---
layout: page
title: 主頁
tagline: 
---
{% include JB/setup %}

<ul>
  {% assign pages_list = site.pages %}  
  {% include JB/pages_list %}
</ul>

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <p>{{ post.excerpt }}</p>
    </li>
  {% endfor %}
</ul>

