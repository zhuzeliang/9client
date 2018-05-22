# html规范

## 文件模版

### PC端

```
<!DOCTYPE html>
<html lang="zh-CN">

<head>
    <meta charset="UTF-8">
    <meta name="keywords" content="全渠道客服，多媒体客服，全渠道智慧互动，大数据采集服务，微信多账号管理，全网评论管理，大数据分析，电商网评，呼叫中心,在线客服,微信开发,微信营销">
    <meta name="description" content="上海久科全球领先的全渠道营销与服务saas平台提供商，涵盖全渠道智慧互动、微信统一管理、全网评论管理平台、大数据采集分析服务等功能模块，为100+家大型品牌客户，包括6家世界500强企业提供的产品与服务。">
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
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, shrink-to-fit=no">
    <meta name="format-detection" content="telephone=no">
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

## 元素属性
不需要为 CSS、JS、html 指定类型属性，HTML5 中默认已包含(注：在jsp文件中和html5属性不被支持，出现报错的情况)

>不需要为 CSS、JS 指定类型属性，HTML5 中默认已包含 

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
