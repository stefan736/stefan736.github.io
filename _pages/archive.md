---
permalink: /archive
layout: page
title: Archive
---


<ul>
  {% for post in site.posts %}
    <li>
      {{ post.date | date: "%Y-%m-%d" }} - <a href=".{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>