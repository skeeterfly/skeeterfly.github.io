---
layout: post
title:  git push同步多个仓库
categories: 诗与远方
tags: git 版本管理 随手记
author: 郭金文
---
* content
{:toc}

## 前言

  最近在使用codingnet仓库。因为之前一直使用github，有些工程想两边同时更新，又不想push两次，有没办法只push一次，实现两边仓库代码的同步呢？



## git同时push到多个仓库
  
编辑本地仓库目录下面的.git目录下的config文件。

添加：

  ```java
  [remote "all"]
  url = https://git.coding.net/XXX/XXX.coding.me.git
  url = https://github.com/XXX/XXX.github.io.git
  ```
再push时，运行

  git push all master


  如果是使用 TortoiseGit 可以直接使用如下：

  ![](/images/skeeterfly/QQ截图20170805092710.jpg)

  push过程，会自动同步两边的代码：

  ![](/images/skeeterfly/QQ截图20170805092747.jpg)