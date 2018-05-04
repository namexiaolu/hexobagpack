---
title: hexo生成博文插入图片
date: 2018-05-03 17:18:15
tags: hexo
---

### 本文转载自：
https://blog.csdn.net/sugar_rainbow/article/details/57415705

<!-- more -->

# RT

十分痛苦，是因为突然发现上传的博客里面的图片居然显示不来，excuse me??? 
![这里写图片描述](https://img-blog.csdn.net/20170226153645068?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvU3VnYXJfUmFpbmJvdw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast) 
笋干shabi了 
怎么办，上网google解决之道，然后又试了很多坑……. 




{% img [class names] https://img-blog.csdn.net/20170226153729569?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvU3VnYXJfUmFpbmJvdw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast %}

{% img [class names] https://img-blog.csdn.net/20170226153729569?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvU3VnYXJfUmFpbmJvdw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast 300px 200px lalal hahah%}

更加绝望了….. 
然后，看到了这个：[dalao指导](http://www.jianshu.com/p/c2ba9533088a) 
hhhh，再试一次…..![这里写图片描述](https://img-blog.csdn.net/20170226153942698?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvU3VnYXJfUmFpbmJvdw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

然而，居然可以了….excuse me??

好吧，总结一下这个牛批的解决办法：

## First

1 把主页配置文件`_config.yml` 里的`post_asset_folder:`这个选项设置为`true`

2 在你的hexo目录下执行这样一句话`npm install hexo-asset-image --save`，这是下载安装一个可以上传本地图片的插件，来自dalao：[dalao的git](https://github.com/CodeFalling/hexo-asset-image)

3 等待一小段时间后，再运行`hexo n "xxxx"`来生成md博文时，`/source/_posts`文件夹内除了`xxxx.md`文件还有一个**同名的文件夹**

## Second

4 最后在`xxxx.md`中想引入图片时，先把图片复制到xxxx这个文件夹中，然后只需要在xxxx.md中按照markdown的格式引入图片：

`![你想输入的替代文字](xxxx/图片名.jpg)`

**注意：** xxxx是这个md文件的名字，也是同名文件夹的名字。只需要有文件夹名字即可，不需要有什么绝对路径。你想引入的图片就只需要放入xxxx这个文件夹内就好了，很像引用相对路径。

5 最后检查一下，`hexo g`生成页面后，进入`public\2017\02\26\index.html`文件中查看相关字段，可以发现，html标签内的语句是`<img src="2017/02/26/xxxx/图片名.jpg">`，而不是`<img src="xxxx/图片名.jpg>`。这很重要，关乎你的网页是否可以真正加载你想插入的图片。

## 总结一下这个跳（试）坑的过程

首先是有句mmp想讲，实在是有点坑

![这里写图片描述](https://img-blog.csdn.net/20170226154012235?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvU3VnYXJfUmFpbmJvdw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

但是，似乎又多了一项学（zhuang）习（bi）技巧![这里写图片描述](https://img-blog.csdn.net/20170226154056704?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvU3VnYXJfUmFpbmJvdw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

hhh，先到这里，后面还有一个坑就是，想引入某些dalao 的链接时，如果链接里包含中文，那么再写入md文件里生成网页后这个链接就打不开了…..

待老夫研究后再填坑，后面如果有时间，就把自己搭建网站的过程码一下。 
![这里写图片描述](https://img-blog.csdn.net/20170226154126642?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvU3VnYXJfUmFpbmJvdw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)