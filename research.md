---
layout: default
title: Research
---

# Research
{% for paper_desc in site.data.papers %}

{% include paper.md paper=paper_desc %}
{% endfor %}

<!--
Latex test: 

$$\int_{c\in\mathcal{C}} \mathbf{Set}(Fc,Gc) \simeq \[\mathcal{C},\mathbf{Set}\](F,G)$$
-->