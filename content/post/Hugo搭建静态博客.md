---
title: "Hugo搭建静态博客"
date: 2019-06-02T19:55:38+08:00
lastmod: 2019-06-02T19:55:38+08:00
draft: false
keywords: [静态博客]
description: "Go语言实现的静态博客生成器"
tags: [Go语言]
categories: [记录]
author: ""

---
[Hugo][]是一款使用[Go][]语言编写的静态网站生成器。

特点: 部署简单,无多余依赖,容易上手.
<!--more-->
## 1. 怎么装
从[官网][]下载二进制文件.解压缩后,将<kbd>hugo</kbd>文件所在目录配进环境变量.

使用
```bash
hugo new site myblog
```
创建属于自己的站点`myblog`

进入`myblog`
通过`hugo server`启动服务.默认访问网址<http://localhost:1313>

此时啥都没有.并且启动服务时,会给出`你应当创建一个模版文件`的提示

## 2. 换个皮肤

注意到生成的博客目录下有个`themes`文件夹,一般主题都放在里边

你可以在[皮肤官网][]挑个痛快.

不过为了尽快体验hugo.不妨使用[hugo][]官网文档中推荐的[Hyde][]

使用(`git`是个好东西:smile:)
```bash
git clone https://github.com/spf13/hyde.git themes/hyde
```

将主题下载至`themes`文件夹中,并记得重命名成较方便的名字
```bash
hugo sever --theme=hyde
```
通过指定主题启动.<http://localhost:1313>

此时因为没有任何文章.页面没有任何内容.
![](https://raw.githubusercontent.com/1urenyang/serutcip/master/hyde%E4%B8%BB%E9%A2%98%E7%A9%BA%E7%99%BD%E9%A1%B5.webp)
但是好歹有了点博客的样子.

考虑到每次启动都要加上 `--theme`来指定主题,比较麻烦

可以修改博客文件夹中的`config.toml`,加入下面的设置
```toml
theme = "hyde"
```
好了, 基本设置结束.开始正题:写点东西

## 3. 写点啥

使用
```bash
hugo new post/示例一.md
```
创建第一篇文章.

> 其中`post`是一般默认存放文档的地方,位于`myblog/content`目录下.

![](https://raw.githubusercontent.com/1urenyang/serutcip/master/hyde%E7%A4%BA%E4%BE%8B%E6%96%87%E7%AB%A0.webp)

一篇简单的示例就完成了.

## 4. 还不够

我们需要更多自定义的功能,那么下一篇接着写.




[Hugo]: https://gohugo.io/
[Go]: https://golang.org/
[官网]: https://github.com/gohugoio/hugo/releases
[皮肤官网]: https://www.gohugo.org/theme/
[Hyde]: https://github.com/spf13/hyde