---
layout: post
title:  com.alibaba.fastjson 高级数据转换
categories: 编程基础
tags: java json处理 工具类
author: 郭金文
---
* content
{:toc}

## fastjson简介

json数据格式是JAVA开发中最常用的数据格式，处理json的工具类很多，fastjson是阿里大牛开发的json快速处理工具类，据说速度比一般的json转换工具类都快。其提供了丰富的json数据格式转换机制。

除了一般的json转换数据格式，如string转json格式，json转string等基础的功能外，还提供了一些比较高级的数据转换能力，我们一起来学习吧。





##String转List<T>

```java	
	String attachStr = "[{'attachBelong': 0,'attachMoudle': 0,'attachType': 0,'fileName': 'balabala.xlsx','formId': 0,'mongoId': 'abcdefghjklmn'}]";
	List<ConstructFormAttachVO> constructFormAttach = JSON.parseArray(attachStr, ConstructFormAttachVO.class);
```


## List<Map> 转换成 List<javaBean>


定义一个实体类对象
	
```java
	public class ConstructFormAttachVO implements Serializable{

		private static final long serialVersionUID = 261784807914369268L;

		private Long attachId;

		public Long getAttachId() {
	    	return this.attachId;
	    }

	    public void setAttachId(Long attachId) {
	        this.attachId = attachId;
	    }
	}
```
	
fastjson将一个List<Map> 转换成 List<javaBean>：

```java
	//构造数据
	List<Map<String, Object>> listMap = new ArrayList<>();
	Map<String, Object> map = new HashMap<>();
	map.put("attachId",1111);
	listMap.add(map);
	//转换
	List<ConstructFormAttachVO> constructFormAttach = JSON.parseArray(listMap.toString(), ConstructFormAttachVO.class);
```
  
