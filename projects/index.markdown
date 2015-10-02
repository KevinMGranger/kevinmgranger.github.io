---
title: Kevin M Granger's Projects
---

{% for proj in site.data.projects %}


{% if proj.url %}
# [{{ proj.name }}]({{ proj.url }})
{% else %}
# {{ proj.name }}
{% endif %}

## {{ proj.type }}

{% if proj.pic %}
![](/img/projects/{{ proj.pic }})
{% endif %}

{{ proj.desc }}


{% endfor %}
