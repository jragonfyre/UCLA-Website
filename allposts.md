---
layout: master
---

{% for post in site.posts %}
[{{ post.title }}]({{ post.url | relative_url }})
{% endfor %}
