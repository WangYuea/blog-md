---
title: js实现单页web应用
---
### 说明
``` bash
当地址栏中的锚点值发生变化的时候 执行对应的处理函数
			1.监听锚点值的变化
			2.获取锚点值
			3.判断锚点值
			4.根据锚点值获取对应的页面
```
### 代码
```bash
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<a href="#index">首页</a>
	<a href="#list">列表页</a>

	<div id="box"></div>

	<script>
		window.onhashchange = function(){
			if(location.hash == "#index"){
				// 获取首页对应的数据
				var xhr = new XMLHttpRequest();
				xhr.open('get','./tpl/index.html',true);
			xhr.send();
				xhr.onreadystatechange = function(){
					if(xhr.readyState == 4){
						if(xhr.status == 200){
							document.getElementById('box').innerHTML = xhr.responseText;
						}
					}
				}
			}else if(location.hash == "#list"){
				// 获取列表页的数据
				var xhr = new XMLHttpRequest();
				xhr.open('get','./tpl/list.html',true);
				xhr.send();
				xhr.onreadystatechange = function(){
					if(xhr.readyState == 4){
						if(xhr.status == 200){
							document.getElementById('box').innerHTML = xhr.responseText;
						}
					}
				}
			}
		}
	</script>
</body>
</html>
```
