---
title:  文章编辑技巧
tags:
  - 其他
comments: true
asset_url: /asset/20201120/
---
**文本编辑**
- 文字突出

《出塞》<br>
秦时明月汉时关，万里长征人未还。<br>
但使龙城 `飞将` 在，不教胡马度阴山。

---

**插入图片**
- html 方式插入图片
    - 优点：可以通过css调整显示格式，同时可以有 `图片批注`。
    - 缺点：嵌套html代码，有点小复杂。
<div class="card mb-3">
    <img class="card-img-top" src="{{site.url}}{{page.asset_url}}wow-map.jpg"/>
    <div class="card-body bg-light">
        <div class="card-text">
            魔兽世界地图 - 图片批注
        </div>
    </div>
</div>

- Markdown 方式插入图片 
    - 优点：方便快捷。
    - 缺点：展示调整空间较小。
    
![魔兽世界地图]({{site.url}}{{page.asset_url}}wow-map.jpg)

---
**代码模块**

{% highlight html %}

<div class="card mb-3">
    <img class="card-img-top" src="https://drscdn.500px.org/photo/127767019/q%3D80_m%3D1500/v2?webp=true&sig=dd1fa4580c459472969cd4992068922f311f12cf263cf08b39615cfc1812286b"/>
    <div class="card-body bg-light">
        <div class="card-text">
            The Peak District on a mosty morning.
        </div>
    </div>
</div>

{% endhighlight %}
