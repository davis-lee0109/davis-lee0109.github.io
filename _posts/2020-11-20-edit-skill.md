---
title:  文章编辑技巧
tags:
  - other
comments: true
asset_url: /asset/20201120/
images:
  - /asset/20201120/wow-map.jpg
  - /asset/20201120/wow-map.jpg
  - /asset/20201120/wow-map.jpg
  - /asset/20201120/wow-map.jpg
---

本文主要是说明不同内容的编辑方式，以及不同方式的优缺点，为以后的文章的编辑作参考用。<br>
主要有**文本编辑**，**图片编辑**，**代码编辑**，**公式编辑**

<!--more-->
---
**文本编辑**

- 文字突出

《出塞》<br>
秦时明月汉时关，万里长征人未还。<br>
但使龙城 `飞将` 在，不教胡马度阴山。

- icon 使用
<p class="d-flex align-items-center">
    <span class="icon grey mr-2" markdown="0">
        {% include entypo/clock.svg %}
    </span>
    灰色左对齐的闹钟标志。
</p>

<p class="d-flex align-items-center">
    红色右对齐的循环标志。
    <span class="icon red ml-2" markdown="0">
        {% include entypo/cycle.svg %}
    </span>
</p>

实现代码

{% highlight markdown %}
{% raw %}

<p class="d-flex align-items-center">
    <span class="icon grey mr-2">
        {% include entypo/clock.svg %}
    </span>
    灰色左对齐的闹钟标志。
</p>

<p class="d-flex align-items-center">
    红色右对齐的循环标志。
    <span class="icon red ml-2">
        {% include entypo/cycle.svg %}
    </span>
</p>

{% endraw %}
{% endhighlight %}

---
**图片编辑**

- html 方式插入`单`图片
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

实现代码
{% highlight html %}
{% raw %}
<div class="card mb-3">
    <img class="card-img-top" src="{{site.url}}{{page.asset_url}}wow-map.jpg"/>
    <div class="card-body bg-light">
        <div class="card-text">
            魔兽世界地图 - 图片批注
        </div>
    </div>
</div>
{% endraw %}
{% endhighlight %}

- Markdown 方式插入`单`图片 
    - 优点：方便快捷。
    - 缺点：展示调整空间较小。
    
![魔兽世界地图]({{site.url}}{{page.asset_url}}wow-map.jpg "魔兽世界大地图")

实现代码
{% highlight markdown %}
{% raw %}
![魔兽世界地图]({{site.url}}{{page.asset_url}}wow-map.jpg "魔兽世界大地图")
{% endraw %}
{% endhighlight %}

- Masonry 方式插入`多`图片 
<div class="card-columns">
    {% for img in page.images %}
    <div class="card">
        <img class="card-img-top" src="{{ img }}" />
    </div>
    {% endfor %}
</div>

实现代码
{% highlight markdown %}
{% raw %}
<div class="card-columns">
    {% for img in page.images %}
    <div class="card">
        <img class="card-img-top" src="{{ img }}" />
    </div>
    {% endfor %}
</div>
{% endraw %}
{% endhighlight %}

- Masonry 方式插入`多`图片，点击查看大图
<div class="card-columns">
    {% for img in page.images %}
    <div class="card" data-toggle="modal" data-target="#exampleModal" data-img="{{ img }}">
        <img class="card-img-top" src="{{ img }}" />
    </div>
    {% endfor %}
</div>
<div class="modal fade" id="exampleModal">
    <div class="modal-dialog modal-lg modal-dialog-centered">
        <div class="modal-content">
            <div class="modal-body">
                <img class="modal-img w-100"/>
            </div>
        </div>
    </div>
</div>
<script type="text/javascript">
  $(document).ready(function() {
    $('#exampleModal').on('show.bs.modal', function (event) {
      var button = $(event.relatedTarget)
      var img = button.data('img')
      var modal = $(this)
      modal.find('.modal-img').attr('src', img)
    })
  })
</script>

实现代码
{% highlight markdown %}
{% raw %}
<div class="card-columns">
    {% for img in page.images %}
    <div class="card" data-toggle="modal" data-target="#exampleModal" data-img="{{ img }}">
        <img class="card-img-top" src="{{ img }}" />
    </div>
    {% endfor %}
</div>

<div class="modal fade" id="exampleModal">
    <div class="modal-dialog modal-lg modal-dialog-centered">
        <div class="modal-content">
            <div class="modal-body">
                <img class="modal-img w-100"/>
            </div>
        </div>
    </div>
</div>

<script type="text/javascript">
  $(document).ready(function() {
    $('#exampleModal').on('show.bs.modal', function (event) {
      var button = $(event.relatedTarget)
      var img = button.data('img')
      var modal = $(this)
      modal.find('.modal-img').attr('src', img)
    })
  })
</script>
{% endraw %}
{% endhighlight %}


- Carousel 方式插入`多`图片
<div id="carouselExampleControls" class="carousel slide mb-4" data-ride="carousel">
    <div class="carousel-inner">
        {% for img in page.images %}
            <div class="carousel-item {% if forloop.first %}active{% endif %}">
                <img src="{{ img }}" class="d-block w-100" alt="">
            </div>
        {% endfor %}
    </div>
    <a class="carousel-control-prev" href="#carouselExampleControls" role="button" data-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="sr-only">Previous</span>
    </a>
    <a class="carousel-control-next" href="#carouselExampleControls" role="button" data-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="sr-only">Next</span>
    </a>
</div>

实现代码
{% highlight markdown %}
{% raw %}
<div id="carouselExampleControls" class="carousel slide mb-4" data-ride="carousel">
    <div class="carousel-inner">
        {% for img in page.images %}
            <div class="carousel-item {% if forloop.first %}active{% endif %}">
                <img src="{{ img }}" class="d-block w-100" alt="">
            </div>
        {% endfor %}
    </div>
    <a class="carousel-control-prev" href="#carouselExampleControls" role="button" data-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="sr-only">Previous</span>
    </a>
    <a class="carousel-control-next" href="#carouselExampleControls" role="button" data-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="sr-only">Next</span>
    </a>
</div>
{% endraw %}
{% endhighlight %}

---
**插入视频**
<iframe src="//player.bilibili.com/player.html?aid=541874959&bvid=BV15i4y1M7uw&cid=228407275&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

---
**代码编辑**

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
---
**公式编辑**
- 行间公式

这是一个行间公式：

$$\sqrt{x^{2}}$$ 

行间公式结束。
{% highlight html %}
这是一个行间公式：

$$\sqrt{x^{2}}$$ 

行间公式结束。
{% endhighlight %}
- 行内公式

这是一个行内公式$\sqrt{x^{2}}$ 
{% highlight html %}
这是一个行内公式$\sqrt{x^{2}}$ 
{% endhighlight %}
