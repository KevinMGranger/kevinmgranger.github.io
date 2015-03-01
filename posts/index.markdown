---
title: Kevin M Granger's Blog
---

{% assign posts = site.posts | sort 'date' %}

{% for post in posts %}

<section><a href="{{ post.url }}">
<h1>{{ post.title }}</h1>
<h2>{{ post.date }}</h2>
<p>{{ post.excerpt }}</p>
</a>
</section>

{% endfor %}
