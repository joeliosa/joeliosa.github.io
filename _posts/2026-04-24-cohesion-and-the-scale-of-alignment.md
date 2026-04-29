---
layout: post
title: "Cohesion and the Scale of Alignment"
date: 2026-04-24
---

**What alignment means for a group**

What does it mean for a group to be aligned? Not in the AI sense — though that question is related — but in the ordinary sense: a team, a community, an institution. When do the members of a group act in ways that are coherent, predictable, and roughly directed toward shared ends?

I have been thinking about this question as an alignment researcher who increasingly suspects the most important alignment problems are not technical. They are problems of coordination, of value plurality, of institutions that must remain stable across time and across people who do not share everything.

The standard move in formal work is to abstract: model agents as rational, preferences as stable, coordination as a fixed-point problem. This gives us beautiful theorems. It gives us much less purchase on what actually happens when a housing cooperative tries to decide how to allocate rooms, or when a research lab tries to maintain a safety culture while growing fast.

What I want to explore in this series is whether formal tools can be made load-bearing in messier settings — not by pretending the messiness away, but by building frameworks that take it seriously as an input. Recent work on democratic fine-tuning and moral graphs suggests this is possible at the level of AI systems;<sup><a href="#ref1" id="back1">1</a></sup> I want to ask whether the same is true for human institutions.

---

**The problem of scale failure**

A useful starting observation: alignment problems at the human scale are almost always problems of *scale failure*. Small groups cohere naturally; it is when they grow that things fall apart. The informal norms that sustained trust at ten people stop working at a hundred. The founder's values diffuse, mutate, get lost in translation through hierarchy.

This is not a new observation. But the alignment community's tools were not designed with it in mind. PAC learning, mechanism design, social choice theory — these frameworks typically either assume small groups where full aggregation is tractable, or large populations where individual preference structure can be averaged away. The interesting regime, the one where most institutional failure actually occurs, is somewhere in between.<sup><a href="#ref2" id="back2">2</a></sup>

What I want is a theory of *cohesion under scale* — one that takes seriously the way shared values propagate, degrade, and sometimes survive the growth of a group.

More soon.

<div class="footnotes">
  <ol>
    <li id="ref1">
      Joe Edelman &amp; Oliver Klingefjord, <a href="https://meaningalignment.substack.com/p/the-first-moral-graph" target="_blank" rel="noopener">"OpenAI x DFT: The First Moral Graph."</a> Meaning Alignment Institute, October 24, 2023. <a href="#back1" class="footnote-backref">↩</a>
    </li>
    <li id="ref2">
      Rosie Bell &amp; Rufus Pollock, <a href="https://metacrisis.info/paper" target="_blank" rel="noopener">"From Polycrisis to Metacrisis: A Short Introduction."</a> Life Itself Sensemaking Studio / Second Renaissance series. <a href="#back2" class="footnote-backref">↩</a>
    </li>
  </ol>
</div>
