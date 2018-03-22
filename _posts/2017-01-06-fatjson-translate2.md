---
layout: post
title:  fastjson 变量驼峰形式与下划线互转
categories: 编程基础
tags: java json处理 工具类 序列化
author: 郭金文
---
* content
{:toc}

## FastJson 支持配置的PropertyNamingStrategy四种策略

属性名策略说明：

CamelCase策略，Java对象属性：personId，序列化后属性：persionId

PascalCase策略，Java对象属性：personId，序列化后属性：PersonId

SnakeCase策略，Java对象属性：personId，序列化后属性：person_id

KebabCase策略，Java对象属性：personId，序列化后属性：person-id

PS:如果是比较旧的版本，CAMEL_CASE_TO_LOWER_CASE_WITH_UNDERSCORES，CAMEL_CASE_TO_LOWER_CASE_WITH_UNDERSCORES两种策略已经不建议使用了。

CAMEL_CASE_TO_LOWER_CASE_WITH_UNDERSCORES，是驼峰转下划线的方式，已经被SnakeCase策略取代了。

下面，我们就介绍常用的驼峰与下划线互转的方法。只要这种方式掌握了，其他的格式序列化方式都是一样的。





##驼峰转下划线

来看一个代码片段：
```java	
	public static String toUnderlineJSONString(Object object) throws JsonProcessingException {
        ObjectMapper mapper = new ObjectMapper();
        mapper.setPropertyNamingStrategy(PropertyNamingStrategy.SNAKE_CASE);
        mapper.setSerializationInclusion(JsonInclude.Include.NON_NULL);
        String reqJson = mapper.writeValueAsString(object);
        return reqJson;
  }
```
object 是一个实体类。经过转换后，变成了下划线形式。

![](/images/skeeterfly/下划线转驼峰1.png)
![](/images/skeeterfly/下划线转驼峰2.png)

## 下划线转驼峰

将下划线格式转成实体类的驼峰形式
	
```java
	public Cssession getCsSession() throws IOException {
        Object resultObject = httpClientHelper.getForEntity(cssessionUrl, Object.class);
        ObjectMapper json = new ObjectMapper();
        json.setPropertyNamingStrategy(PropertyNamingStrategy.SNAKE_CASE);
        String params = json.writeValueAsString(resultObject);
        Cssession cssession = json.readValue(params, Cssession.class);
        return cssession;
    }
```
resultObject 请求回来的数据是一个下划线格式的数据

将其变成一个实体类的驼峰形式。

![](/images/skeeterfly/驼峰转下划线1.png)
![](/images/skeeterfly/驼峰转下划线2.png)

  
