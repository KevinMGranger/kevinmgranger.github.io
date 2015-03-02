---
title: Kevin M Granger's Blog
---

{% for post in site.posts %}

<section><a href="{{ post.url }}">
<h1>{{ post.title }}</h1>
<p><small>{{ post.date }}</small></p>
<p>{{ post.excerpt }}</p>
</a>
</section>

{% endfor %}
