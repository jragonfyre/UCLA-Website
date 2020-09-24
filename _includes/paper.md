<div class="paper-div text-container" markdown="1">
<span class="paper-title"> {{ include.paper.title }} </span>

[arxiv]({{ include.paper.arxiv_url }}){: .arxiv-link }

{% if include.paper.other_authors %}
With {{ include.paper.other_authors }}. {% endif %}{% if include.paper.accepted %}Accepted for publication in {{ include.paper.publisher }}. {% endif %}{{ include.paper.description }}
</div>