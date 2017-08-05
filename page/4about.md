---
layout: page
title: 关于本博客
permalink: /about/
icon: users
type: page
---

* content
{:toc}

## 团队成员
<ul>
{% for author in site.pages %}
	{%if author.author_name %}
		<li>
			<a href='{{ author.page_path }}'>{{ author.author_name | remove: ' '}}</a>
		</li>
	{%endif%}
{% endfor %}
</ul>
## 联系我们

* 个人主页：[skeeterfly.coding.me]()
* Email：jeevan0612@qq.com

## 更新日志

* 2017.1.1 博客上线

## 友情链接

[还没有友情链接丫丫](http://baidu.com)


