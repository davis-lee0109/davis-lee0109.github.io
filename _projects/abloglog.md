---
title: 博客开发进度 - 2020/11
---
## 下一步计划
正常撰写博客

## 2020-11-24
今天完成三项内容：
1. 添加不蒜子页面统计代码。
2. 新增导航栏目。
3. 添加百度站内搜索功能。

**添加[不蒜子](http://ibruce.info/2015/04/04/busuanzi/)访问统计代码。**

* `_includes/structure/head.html` 添加不蒜子js代码

```html
<script async src="//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js"></script>
```

* `_includes/bars/side.html` 添加总访问量和总uv量显示代码

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

* `_includes/components/post-meta.html` 添加文章阅读量显示代码

```html
<div class="card bg-light">
    <div class="card-body text-center">
        <span id="busuanzi_container_page_pv" style='display:none'>
            本文总阅读量<span id="busuanzi_value_page_pv"></span>次
        </span>
    </div>
</div>
```

**添加新导航栏** 
* `_config.yml` 添加 `collection` 和 `default.setting`

```yml
collections:
  books:
    output: true
    title: Books
    permalink: /:collection/:name.html

default
  -
    scope:
      path: "_books"
    values:
      show_profile: false
      layout: defaults/project
# 此处直接借用 project 的 laylout，以后可以针对需求再调整
```

* `_data/nav.yml` 添加 导航名称 和 连接

```yml
- title: 阅读
  href: list/books.html
```

* 根目录下新建文件夹`_books`，该栏目文章都放在这下面。

* `list`目录下新建`books.md`，用来展示栏目首页。

**添加百度站内搜索功能** 

* `_includes/structure/head.html` 添加 百度搜索js代码。

```javascript
<SCRIPT language=javascript>
    <!--
    function go(formname)
    {
     var url = "http://www.baidu.com/baidu";
     formname.method = "get";
    if (formname.myselectvalue.value == "1") {
      document.search_form1.word.value = document.search_form1.word.value+" site:davis-lee0109.github.io";
    }
    formname.action = url;
    return true;
    }
    //-->
</SCRIPT>
```

* `_includes/bars/side.html` 添加 百度搜索框代码。

```html
<br>
<div class="card bg-light">
    <div class="card-body text-center">
        <form name="search_form1" target="_blank" onsubmit="return go(this)">
            <input name=word size="20" value="请输入关键字" onMouseOver="this.focus()"
                   onBlur="if (value ==''){value='请输入关键字'}" onFocus="this.select()"
                   onClick="if(this.value=='请输入关键字')this.value=''">
            <input type="submit" value="百度站内搜索"><br>
            <INPUT name=myselectvalue type=hidden value=1>
        </form>
    </div>
</div>
```

## 2020-11-23
今天完成一项内容：
1. 添加[谷歌分析](https://analytics.google.com/analytics/web/)统计代码。

* `_includes/structure/head.html` 添加谷歌分析代码

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=G-1LC3HC05B8"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-1LC3HC05B8');
</script>
```

## 2020-11-22
今天完成三项内容：
1. 博客完成基本搭建。
2. 增加 [intensedebate](https://www.intensedebate.com) 评论功能。
3. 增加了[百度统计](https://tongji.baidu.com)功能。

* `_layouts/defaults/post.html`  增加了评论功能。

```html
<hr>
<br>
{% if site.intensedebate_comments %}
{% include intensedebate-comments.html %}
{% endif %}
```

* `_includes/structure/head.html` 添加百度统计js代码。

```javascript
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