---
title: Hexo博客插入图片（二）
date: 2018-05-03 17:51:48
tags: hexo
---

### 为啥写了个二

上次搞定本地插入图片后，发现 复制别的文章的时候，网络图片有时候加载不出来（大多数情况）。

<!-- more -->

### 开始搞

我觉得看看官方文档怎么写的 https://hexo.io/zh-cn/docs/tag-plugins.html

他在image中写的代码是这样的 

​     在文章中插入指定大小的图片。

```
{% img [class names] /path/to/image [width] [height] [title text [alt text]] %}
```

指定大小？？？？意思就是把width和height改了就好了？

结果根本不是这样的。是这样的：

{% img [class names] https://img-blog.csdn.net/20170226153942698?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvU3VnYXJfUmFpbmJvdw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast [300][200] [title text [alt text]] %}

我就f了个大k了。

只好简单使用

```html
{% img [class names] https://img-blog.csdn.net/20170226153942698?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvU3VnYXJfUmFpbmJvdw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast %}
```
就好了。
{% img  https://img-blog.csdn.net/20170226153942698?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvU3VnYXJfUmFpbmJvdw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast %}

### 总结
所以 以后 就用
```
{% img url}
```
来插入图片了
