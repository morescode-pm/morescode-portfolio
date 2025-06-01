---
layout: page
title: Portfolio
---

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <br>
      <small>Tags: {{ post.tags | join: ', ' }}</small>
    </li>
  {% endfor %}
</ul>