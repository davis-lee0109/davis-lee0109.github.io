---
layout: defaults/page
permalink: index.html
narrow: true
title: “无用之用，方为大用”
---

“无用之用，方为大用”


Recent Posts

{% for post in site.posts limit:3 %}
{% include components/post-card.html %}
{% endfor %}


