---
layout: default
title: Research
---

# Research


# Papers
{% for paper_desc in site.data.papers %}

{% include paper.md paper=paper_desc %}
{% endfor %}



