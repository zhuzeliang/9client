# css 规范

## 重置样式

### PC端

```
html, body, div, h1, h2, h3, h4, h5, h6, p, dl, dt, dd, ol, ul, li, fieldset, form, label, input, legend, table, caption, tbody, tfoot, thead, tr, th, td, textarea, article, aside, audio, canvas, figure, footer, header, mark, menu, nav, section, time, video { margin: 0; padding: 0; }
h1, h2, h3, h4, h5, h6 { font-size: 100%; font-weight: normal }
article, aside, dialog, figure, footer, header, hgroup, nav, section, blockquote { display: block; }
ul, ol { list-style: none; }
img { border: 0 none; vertical-align: top; }
blockquote, q { quotes: none; }
blockquote:before, blockquote:after, q:before, q:after { content: none; }
table { border-collapse: collapse; border-spacing: 0; }
strong, em, i { font-style: normal; font-weight: normal; }
ins { text-decoration: underline; }
del { text-decoration: line-through; }
mark { background: none; }
input::-ms-clear { display: none !important; }
body { font: 12px/1.5 \5FAE\8F6F\96C5\9ED1, \5B8B\4F53, "Hiragino Sans GB", STHeiti, "WenQuanYi Micro Hei", "Droid Sans Fallback", SimSun, sans-serif; background: #fff; }
a { text-decoration: none; color: #333; }
a:hover { text-decoration: underline; }
```

### 移动端

```
* { -webkit-tap-highlight-color: transparent; outline: 0; margin: 0; padding: 0; vertical-align: baseline; }
body, h1, h2, h3, h4, h5, h6, hr, p, blockquote, dl, dt, dd, ul, ol, li, pre, form, fieldset, legend, button, input, textarea, th, td { margin: 0; padding: 0; vertical-align: baseline; }
img { border: 0 none; vertical-align: top; }
i, em { font-style: normal; }
ol, ul { list-style: none; }
input, select, button, h1, h2, h3, h4, h5, h6 { font-size: 100%; font-family: inherit; }
table { border-collapse: collapse; border-spacing: 0; }
a { text-decoration: none; color: #666; }
body { font-size: 14px; fon-family: -apple-system,Helvetica,sans-serif; line-height: 1.5; color: #666; -webkit-text-size-adjust: 100% !important; text-size-adjust: 100% !important; }
input[type='submit'],button, textarea, input[type='tel'], input[type='date'], input[type='password'], input[type='text'], input[type='radio'], input[type='button'], select { -webkit-appearance: none; -moz-appearance: none; appearance: none; }
```

## 团队约定

> 样式文件必须写上 @charset 规则，并且一定要在样式文件的第一行首个字符位置开始写，编码名用 "UTF-8",引号用双引号,避免莫名问题

推荐：

```
@charset "UTF-8";

.demo{

}
```

不推荐：

```
/**
 * @desc File Info
 * @author Author Name
 * @date 2018-05-22
 */
 
/* @charset规则不在文件首行首个字符开始 */

@charset "UTF-8";

.demo{

}
```

## 代码格式化

> 代码大小写，团队约定不适用驼峰命名，全部小写

推荐：

```
.demo{
	display:block;
}
```

不推荐：

```
.DEMO{
	display:block;
}
```

> 选择器

* 尽量少用通用选择器 
* 不使用 ID 选择器
* 不使用无具体语义定义的标签选择器
* 每个属性末尾都加分号

推荐：

```
.chat{
	display:block;
}
.chat .chat-right{
	display:block;
}
.chat .chat-right .chat-right-num{
	display:block;
}
```

不推荐：

```
.chat{
	display:block;
}
.chat div{
	display:block;
}
.chat .chat-right span{
	display:block;
}
```

> 属性能用缩写尽量用缩写

推荐：

```
body{
	background: #00ff00 url('go.gif') no-repeat fixed center; 
}
```

不推荐：

```
body{
	background-color:#00ff00;
	background-image:url('go.gif');
	background-repeat:no-repeat;
	background-attachment:fixed;
	background-position:center; 
}
```

## sass规范

### 团队约定

> 严格遵守上面 “CSS规范” 中的 “编码规范”
> SASS有两种语法格式，一种是 SCSS (Sassy CSS)，另一种是缩进格式（Indented Syntax），有时称之为 Sass；考虑到 SCSS 语法对 CSS 语法友好的兼容性和扩展性，我们在使用 SASS 编写样式的时候，统一使用 SCSS 语法
> 公共mixins.scss文件，包含共用变量，及共用方法

例：

```
@charset "UTF-8";

$main-color:#337ab7;
$sub-font-color: #606266;
$main-font-color: #24292e;
$em-color:#c93838;
$border-color:#eee;
@mixin clearfix
{
    &:after
    {
        display: block;
        clear: both;
        height: 0;
        content: '\200B';
    }
}

@mixin clamp($value)
{
    display: -webkit-box;
    overflow: hidden;
    text-overflow: ellipsis;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: $value;
}

@mixin ellipsis
{
	white-space:nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

注：可根据实际项目开发添加适合自己的共用方法


