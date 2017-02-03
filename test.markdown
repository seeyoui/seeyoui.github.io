---
layout: default
---

{% for post in site.posts reversed limit:1 offset:1 %}
	{{ post.title }}
{% endfor %}