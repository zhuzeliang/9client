# html规范

## 文件模版

### PC端

```
<!DOCTYPE html>
<html lang="zh-CN">

<head>
    <meta charset="UTF-8">
    <meta name="keywords" content="your keywords">
    <meta name="description" content="your description">
    <meta http-equiv="X-UA-Compatible" content="IE=Edge,chrome=1">
    <meta name="renderer" content="webkit">
    <title>PC端HTML模版</title>
    <!-- S DNS预解析 -->
    <link rel="dns-prefetch" href="">
    <!-- E DNS预解析 -->
    <!-- S 样式引入 -->
    <link rel="stylesheet" href="css/index.css">
    <!-- E 样式引入 -->
</head>

<body>
</body>

</html>
```

### 移动端

```
<!DOCTYPE html>
<html lang="zh-CN">

<head>
    <meta charset="UTF-8">
    <meta name="keywords" content="your keywords">
    <meta name="description" content="your description">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, shrink-to-fit=no">
    <meta name="format-detection" content="telephone=no">
    <meta name="format-detection" content="email=no">
    <title>移动端HTML模版</title>
    <!-- S DNS预解析 -->
    <link rel="dns-prefetch" href="">
    <!-- E DNS预解析 -->
    <!-- S 样式引入 -->
    <link rel="stylesheet" href="css/index.css">
    <!-- E 样式引入 -->
</head>

<body>
</body>

</html>
```

注：keywords description 可根据实际seo需求而定。

## 元素属性

不需要为 CSS、JS、html 指定类型属性，HTML5 中默认已包含(注：在jsp文件中一些html5属性不被支持，出现报错的情况)

>不需要为 CSS、JS 指定类型属性，HTML5 中默认已包含 

* js css 外链

推荐：

```
<link rel="stylesheet" href="" >
<script src=""></script>
```

不推荐：

```
<link rel="stylesheet" type="text/css" href="" >
<script type="text/javascript" src="" ></script>
```

* 标签

推荐：

```
<input type="text">	
<input type="radio" name="name" checked="checked" >
```

不推荐：

```
<input type=text>	
<input type='text'>
<input type="radio" name="name" checked >
```

## html代码书写风格

> html、css 对大小写不敏感，团队统一使用小写，统一使用“-”连接

推荐：

```
<div class="chat">
	<div class="chat-name"></div>
	<div class="chat-num"></div>
</div>
```

不推荐：

```
<div class="chat">
	<div class="chatName"></div>
	<div class="chatNum"></div>
</div>
```

> 代码嵌套，块状元素嵌套行内元素的风格,块状元素单独一行，行内元素可选

推荐：

```
<div>
    <h1></h1>
    <p></p>
</div>	
<p><span></span><span></span></p>
```

不推荐：

```
<div>
    <h1></h1><p></p>
</div>	
<span><div></div></span>
```

## html 代码注释

> 单行注释

推荐：

```
<!-- Comment Text -->
<div>...</div>
```

不推荐：

```
<div>...</div><!-- Comment Text -->	
	
<div><!-- Comment Text -->
    ...
</div>
```

> 模块注释

推荐：

```
<!-- S module A -->	
<div class="module-a">
    ...
</div>
<!-- E module A -->

<!-- S module B -->	
<div class="module-b">
    ...
</div>
<!-- E module B -->
```


不推荐：

```
<!-- S module A -->	
<div class="module-a">
    ...
</div>
<!-- E module A -->
<!-- S module B -->	
<div class="module-b">
    ...
</div>
<!-- E module B -->
```


