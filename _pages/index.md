---
layout: defaults/page
permalink: index.html
narrow: true
title: Welcome to Davis' Blog
---

文章栏目中记载一些平时工作生活中的所思所想。

|Tag|说明|
|----|:----|
|数学|数学在工作生活中的应用。|
|理财|理财中遇到的误区及解决方法。|
|程序|一些程序方面的问题。|
|其他|就是其他|


|-----------------+------------+-----------------+----------------|
| Default aligned |Left aligned| Center aligned  | Right aligned  |
|-----------------|:-----------|:---------------:|---------------:|
| First body part |Second cell | Third cell      | fourth cell    |
| Second line     |foo         | **strong**      | baz            |
| Third line      |quux        | baz             | bar            |
|-----------------+------------+-----------------+----------------|
| Second body     |            |                 |                |
| 2 line          |            |                 |                |
|=================+============+=================+================|
| Footer row      |            |                 |                |
|-----------------+------------+-----------------+----------------|

资料栏目中主要是一些平时经常使用的资料和来源等。

Recent Posts

{% for post in site.posts limit:3 %}
{% include components/post-card.html %}
{% endfor %}


