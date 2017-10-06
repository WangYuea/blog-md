---
title: artTemplate的简单用法
---
### 用法一：使用渲染模板

需要先使用一个type="text/html"的script标签存放模板
#### 1.简单的json数据
``` bash
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>
        <script type="text/javascript" src="js/template.js" ></script>
    </head>
    <body>
        <div id="container"></div>
        <script type="text/html" id="div">
            <h1>{{name}}</h1>
            <h2>{{age}}</h2>
        </script>
        <script type="text/javascript">
            var data = {
                name:"geekWeb",
                age:22
            }
            var html = template('div',data);
            document.getElementById("container").innerHTML = html;
        </script>
    </body>
</html>  
```
注：数据中的k用{{}}包装！
#### 2.带数组的json数据
```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>
        <script type="text/javascript" src="js/template.js" ></script>
    </head>
    <body>
        <div id="container"></div>
        <script type="text/html" id="div">
            <h1>{{name}}</h1>
            <ul>
                {{each lang as value i}}
                <li>语言{{i+1}}:{{value}}</li>
                {{/each}}
            </ul>
        </script>
        <script type="text/javascript">
            var data = {
                name:"前端语言",
                lang:['html','css','js']
            }
            var html = template('div',data);
            document.getElementById("container").innerHTML = html;
        </script>
    </body>
</html>
```
注：通过each遍历数组，value和i分别表示值与索引，使用时千万注意：each中value和i的顺序性不能颠倒，先用value后用i
#### 3.数组中包含对象的json数据
```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>
        <script type="text/javascript" src="js/template.js" ></script>
    </head>
    <body>
        <div id="container"></div>
        <script type="text/html" id="div">
            <h1>{{name}}</h1>
            <ul>
                {{each lang}}
                <li>语言:{{$value.title}} 定义:{{$value.add}}</li>
                {{/each}}
            </ul>
        </script>
        <script type="text/javascript">
            var data = {
                name:"前端语言",
                lang:[{
                    title:"html",
                    add:"超文本标记语言"
                },{
                    title:"css",
                    add:"层叠样式表"
                },{
                    title:"javaScript",
                    add:"添加动态特效"
                }]
            }
            var html = template('div',data);
            document.getElementById("container").innerHTML = html;
        </script>
    </body>
</html>  
```
注：使用each遍历不需要value和i，但是在使用值的时候要用$value
### 用法二：使用渲染函数
不需要先使用script标签存放模板
```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>
        <script type="text/javascript" src="js/template.js" ></script>
    </head>
    <body>
        <div id="container"></div>
        <script type="text/javascript">
            var data = {
                name:"geekWeb",
                age:22
            }
            var source = '<h1>{{name}}</h1>'+'<h2>{{age}}</h2>';
            var render = template.compile(source);
            var html = render(data);
            document.getElementById("container").innerHTML = html;
        </script>
    </body>
</html>
```
可以理解成将渲染模板放在source中。其余数据用法一致！