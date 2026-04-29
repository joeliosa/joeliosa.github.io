---
layout: default
---

<div class="home-columns">
  <figure class="home-image">
    <img src="{{ '/assets/hero.png' | relative_url }}" alt="Newscientist Issue 3206 by Tishk Barzanji">
    <figcaption>'Newscientist Issue 3206' by Tishk Barzanji</figcaption>
  </figure>

  <div class="home-text">
    <p>I'm working to build the infrastructure and tools that helps human systems, markets, and AI learn and act on what they actually value. See more in my <a href="#">white paper</a>.</p>
  </div>
</div>

<div class="home-writing">
  <h2>Writing</h2>
  <ul class="post-list">
    {% for post in site.posts limit:6 %}
    <li class="post-item">
      <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
      <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
    {% endfor %}
  </ul>
</div>
