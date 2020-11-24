---
title: 博客开发进度
---
## 下一步计划
正常撰写博客

## 2020-11-24
1. 添加[不蒜子](http://ibruce.info/2015/04/04/busuanzi/)访问统计代码。

* js 代码 - "_includes/structure/head.html"

```html
<script async src="//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js"></script>
```

* 总访问量和总uv量 - "_includes/bars/side.html"

```html
<br>
<div class="card bg-light">
    <div class="card-body text-center">
        <span id="busuanzi_container_site_pv" style='display:none'>
            本站总访问量<span id="busuanzi_value_site_pv"></span>次
        </span>
        <br>
        <span id="busuanzi_container_site_uv" style='display:none'>
            本站访客数<span id="busuanzi_value_site_uv"></span>人次
        </span>
    </div>
</div>
```

* 文章阅读量 - "_includes/components/post-meta.html"

```html
<div class="card bg-light">
    <div class="card-body text-center">
        <span id="busuanzi_container_page_pv" style='display:none'>
            本文总阅读量<span id="busuanzi_value_page_pv"></span>次
        </span>
    </div>
</div>
```


## 2020-11-23
### 完成进展
1. [谷歌分析](https://analytics.google.com/analytics/web/)代码添加完毕。
"_includes/structure/head.html"

```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-1LC3HC05B8"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-1LC3HC05B8');
</script>
```

## 2020-11-22
### 完成进展：
* 博客完成基本搭建。
* 增加了评论功能。目前的问题是 [intensedebate](https://www.intensedebate.com) 网络访问有些不稳定。
"_layouts/defaults/post.html"

```html
<hr>
<br>
{% if site.intensedebate_comments %}
{% include intensedebate-comments.html %}
{% endif %}
```

* 增加了[百度统计](https://tongji.baidu.com)功能。
"_includes/structure/head.html"

```html
<script>
    var _hmt = _hmt || [];
    (function() {
      var hm = document.createElement("script");
      hm.src = "https://hm.baidu.com/hm.js?f4ca4497f01646c9d3ccffd89fbbbed3";
      var s = document.getElementsByTagName("script")[0];
      s.parentNode.insertBefore(hm, s);
    })();
</script>
```