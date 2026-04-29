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

    <p>I'm also a PhD student in logic and philosophy at IRIT/CNRS, working on ways to formally distinguish between normative/ethical and empirical knowledge, and actively trying to realize more practical applications of this work (as also seen in the above white post).</p>

    <p>Some of my older, less-polished writing is available on <a href="https://nspaces.blogspot.com/" target="_blank">Negative Spaces</a>, should you feel inclined to look :-)</p>
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
