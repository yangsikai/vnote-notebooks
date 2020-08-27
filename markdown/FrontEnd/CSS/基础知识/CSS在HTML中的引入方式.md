# CSS在HTML中的引入方式

## 从外部引入CSS文件

| 属性 |                说明                |
| ---- | ---------------------------------- |
| rel  | 定义当前文档与被链接文档之间的关系 |
| href | 外部样式文件                       |
| type | 文档类型                           |

```
<link rel="stylesheet" href="xxx.css" type="text/css">
```

## 写在style标签中

## 写在元素的style属性中

## 导入样式
使用 `@import` 可以在原样式规则中导入其他样式表，可以在外部样式、style标签中使用。

导入样式要放在样式规则前面定义。

## demo
```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <title>引入方式</title>
    <style>
        #in {
            /* CSS的注释 */
            width: 100px;
            height: 100px;
            border: 3px dashed blue;
        }
    </style>
    <!--
        通过文件加载，可以利用浏览器缓存，加快网页的访问速度
    -->
    <link rel="stylesheet" href="../css/001-style.css">
</head>
<body>
    <!--行内样式-->
    <div style="width:200px;height:200px;border:1px solid red;">inner</div>
    <div id="in">in</div>
    <div id="out">out</div>
</body>
</html>
```