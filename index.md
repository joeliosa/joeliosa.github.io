---
layout: default
---

<div class="home-columns">
  <figure class="home-image">
    <img src="{{ '/assets/hero.png' | relative_url }}" alt="Newscientist Issue 3206 by Tishk Barzanji">
    <figcaption>'Newscientist Issue 3206' by Tishk Barzanji</figcaption>
  </figure>

  <div class="home-text">
    <p>I'm working to build the infrastructure and tools that helps human systems, markets, and AI learn and act on what they actually value. See more in my <a href="{% post_url 2026-07-05-scales-of-alignment %}">"white post"</a>.</p>

    <p>I'm also a PhD student in logic and philosophy at IRIT/CNRS, working on ways to formally distinguish between normative/ethical and empirical knowledge, and actively trying to realize more practical applications of this work (as also seen in the above white post).</p>

    <p>At this point, my writings are a bit scattered around all different corners of the web, ranging from denser and technical to airy and conceptual (with some of it previewed on the bottom of this page). See <a href="/research#writing">this</a> little directory where all of them are organized.</p>

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
