---
layout: default
title: Research
---

# Research

<div markdown="1" class="text-container container bg-light">

My current research interests are homotopy theory, algebraic geometry, and number theory.
</div>

# Papers and Preprints
{% for paper_desc in site.data.papers %}

{% include paper.md paper=paper_desc %}
{% endfor %}



