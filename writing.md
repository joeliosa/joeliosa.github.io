---
layout: default
title: Writing
---

<h1>Writing</h1>

<p>I write about alignment, coordination, values, and the ways formal ideas relate to real human systems. Occasional notes on philosophy and method.</p>

<ul class="post-list">
  {% for post in site.posts %}
  <li class="post-item">
    <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
    <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </li>
  {% endfor %}
</ul>
