
<div class="text-container container bg-light" markdown="1">

#### Research Interests
- Homotopy Theory
- Algebraic Geometry
- Number Theory

#### Past Papers
{% for paper in site.data.papers %}
- [{{ paper.title }}]({{ 'research.html' | relative_url }}#{{paper.id}})
  {% if paper.accepted and paper.year %}({{paper.year}})
  {% endif %}{% if paper.arxiv_url %}[\[arxiv\]]({{ paper.arxiv_url }}){: target="_blank" }
  {% endif %}{% if paper.pdf_path %}[\[pdf\]]({% link {{paper.pdf_path}} %}){: target="_blank" }
  {% endif %}
{% endfor %}

</div>
