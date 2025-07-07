<div markdown="1" class="container text-container bg-light">

{% if include.post.latex-title %}
#### [{{ include.post.latex-title }}]({{ include.post.url | relative_url }})
{% elsif include.post.title %}
#### [{{ include.post.title }}]({{ include.post.url | relative_url }})
{% else %}
#### [Missing Title]({{include.post.url | relavite_url}})
{% endif %}

{% if include.post.author %}<span class="author-name">{{ include.post.author }}</span>
{% endif %}

{{ include.post.summary }}

</div>