---
layout: post
title:  项目自动化构建（一）gradle简介及配置
categories: 项目框架
tags: gradle maven 自动化构建 项目构建 专题
author: 郭金文
---
* content
{:toc}

## gradle简介

Gradle是一个基于Apache Ant和Apache Maven概念的项目自动化构建工具。它使用一种基于Groovy的特定领域语言(DSL)来声明项目设置，抛弃了基于XML的各种繁琐配置。配置文件的格式都遵循groovy语言，区别于maven等其他主流构建工具的是，用其构建项目显得更加便捷，且非常灵活。






## Gradle 安装 及 环境配置


 环境：windows

 安装JDK，并配置JAVA_HOME环境变量。因为Gradle是用Groovy编写的，而Groovy基于JAVA。另外，Java版本要不小于1.5.

 上官网下载最新的gradle包，地址：http://services.gradle.org/distributions/
 目前最新版本应该是4.0，本篇文章中采用2.2.如果需要高版本的gradle，需要安装对应的更高版本的jdk，具体的版本对照，可以参考官网。

 如果gradle官网连不上时，可以上其他gradle包下载地址：http://download.csdn.net/album/detail/2265

 下载完gradle包后，解压。。

 目录：D:\gradle-2.2.1-all\gradle-2.2.1

 打开windows系统设置，环境变量》系统变量》path，在path中添加路径：D:\gradle-2.2.1-all\gradle-2.2.1\bin

 ![](/images/skeeterfly/QQ截图20170808224708.jpg)

 打开命令窗口，输入

 	gradle -v 
 
 提示信息，

 ![](/images/skeeterfly/QQ截图20170808224933.jpg).


 环境配置完成。


  
