---
layout: default
---

<div class="intro">
  <p>I am a PhD student at <a href="https://www.irit.fr" target="_blank" rel="noopener">IRIT, Université de Toulouse</a>, working on ethical AI and alignment. My research sits at the intersection of formal methods, multi-agent systems, and the theory of responsibility.</p>

  <p>I am broadly interested in how formal tools — from game theory to PAC learning to mechanism design — can be made to bear on real problems in human coordination and institutional design. I think carefully about values: how to elicit them, represent them, and build systems that remain faithful to them at scale.</p>

  <p>I am moving to Graz, Austria in 2026.</p>
</div>

<div class="home-section">
  <h2>Recent writing</h2>
  <ul class="post-list">
    {% for post in site.posts limit:4 %}
    <li class="post-item">
      <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
      <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
    {% endfor %}
  </ul>
</div>

<div class="home-section">
  <h2>Current work</h2>
  <ul class="paper-list">
    <li class="paper-item">
      <p class="paper-title">PAC Learnability of Responsibility Attribution in Boolean Games</p>
      <p class="paper-meta">Working paper &mdash; 2026</p>
      <p class="paper-abstract">We adapt PAC learning theory to formalize when responsibility notions over Boolean games are efficiently learnable, connecting causal attribution to sample complexity bounds.</p>
      <div class="paper-links">
        <a href="#">Draft coming soon</a>
      </div>
    </li>
  </ul>
</div>
