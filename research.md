---
layout: default
title: Research
---

# Research

<div markdown="1" class="text-container container bg-light">

My research is in the field of algebraic topology, specifically homotopy theory 
and equivariant algebra. As a graduate student I worked on power operations in 
Adams-like spectral sequences as well as the algebra of Green and Tambara functors,
which are equivariant analogs of rings. 
For more details see my [research statement]({% link pdfs/schuchardt-research-statement.pdf %}){: target="_blank"}.

</div>

# Papers and Preprints
{% for paper_desc in site.data.papers %}

{% include paper.md paper=paper_desc %}
{% endfor %}



