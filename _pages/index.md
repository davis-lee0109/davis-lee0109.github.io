---
layout: defaults/page
permalink: index.html
narrow: true
title: Welcome to Davis' Blog
---
<div class="card mb-3">
    <img class="card-img-top" src="/asset/index/waitan.jpg"/>
    <div class="card-body bg-light">
        <div class="card-text">
            梦从这里启航……
        </div>
    </div>
</div>

[**文章**]({{site.utl}}list/posts.html) 栏目中记载一些平时工作生活中的所思所想。

|Tag|说明|
|:----:|:----|
|math|数学在工作生活中的应用。|
|finance|理财中遇到的误区及解决方法。|
|IT|一些程序方面的问题。|
|others|就是其他|

<br>

[**资料**]({{site.utl}}list/projects.html) 栏目中主要是一些平时经常使用的资料和来源等。

***
#### 最近发布

{% for post in site.posts limit:3 %}
{% include components/post-card.html %}
{% endfor %}


