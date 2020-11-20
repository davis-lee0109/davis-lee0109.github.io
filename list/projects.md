---
title: 资料集合
narrow: true
permalink: list/projects.html
show_profile: ture
---

{% for project in site.projects %}
- [{{ project.title }}]({{ site.baseurl }}{{ project.url }})
{% endfor %}
