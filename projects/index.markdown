---
title: Kevin M Granger's Projects
---

{% for proj in site.data.projects %}


# {{ proj.name }}

## {{ proj.type }}

{% if proj.pic %}
![](/img/projects/{{ proj.pic }})
{% endif %}

{{ proj.desc }}


{% endfor %}
