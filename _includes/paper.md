<div class="paper-div text-container" markdown="1">
<span class="paper-title" id="{{include.paper.id}}"> {{ include.paper.title }} </span>
{% if include.paper.accepted and include.paper.year %}({{include.paper.year}}){% endif %}

[\[arxiv\]]({{ include.paper.arxiv_url }}){: target="_blank" }
[\[pdf\]]({% link {{include.paper.pdf_path}} %}){: target="_blank" }

{% if include.paper.other_authors %}
With {{ include.paper.other_authors }}. {% endif %}{% if include.paper.accepted %}Accepted for publication in {{ include.paper.publisher }}. {% endif %}{{ include.paper.description }}
</div>