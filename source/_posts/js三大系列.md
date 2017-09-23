---
title: js的三大系列
date: 2016-08-20
---
### offset系列
#### offset系列的5个属性
1. offsetLeft : 用于获取元素到最近的定位父盒子的左侧距离
    计算方式: 当前元素的左边框的左侧到定位父盒子的左边框右侧
    如果父级盒子没有定位, 那么会接着往上找有定位的盒子
    如果上级元素都没有定位,那么最后距离是与body的left值
2. offsetTop : 用于获取元素到最近定位父盒子的顶部距离
    计算方式:当前元素的上边框的上侧到定位父盒子的上边框下侧
    如果父级盒子没有定位,那么会接着往上找有定位的盒子
    如果上级元素都没有定位,那么最后距离是与body的top值

3. offsetWidth :用于获取元素的真实宽度(除了margin以外的宽度)

4. offsetHeight : 用于获取元素的真实高度(除了margin以外的高度)

5. offsetParent :用于获取该元素中有定位的最近父级元素
    如果当前元素的父级元素都没有进行定位,那么offsetParent为body
 #### 与style.(left/top/width/height)的区别:
 1. offset系列的是只读属性,而通过style的方式可以读写
 2. offset系列返回的数值类型(结果四舍五入),style返回的是字符串
 3. offsetLeft 和 offsetTop 可以返回没有定位的元素的left值和top值,而style不可以

#### scroll系列
#### scroll系列的4个属性
1. scrollHeight :元素中内容的实际高度(没有边框)
    * 如果内容不足,就是元素的高度

2. scrollWidth: 元素中内容的实际宽度(没有边框)
    * 如果内容不足,就是元素的宽度

3. scrollTop: onscroll事件发生时,元素向上卷曲出去的距离

4. scrollLeft : onscroll事件发生时,元素向左卷曲出去的距离
#### 兼容问题
(1) 兼容问题
* 未声明 DTD: 谷歌,火狐,IE9+支持
```
  document.body.scrollTop/scrollLeft
```
* 已经声明DTD:IE8以下支持
```
 document.documentElement.scrollTop/scrollLeft
```
* 火狐/谷歌/ie9+以上支持的
```
  window.pageYOffest/pageXOffest
```
(2) 兼容代码
```
function getScroll() {
        return {
            left:window.pageXOffset||document.body.scrollLeft||document.documentElement.scrollLeft||0,
           top:window.pageYOffset||document.body.scrollTop||document.documentElement.scrollTop||0
        };
    }

```
#### 使用方法：
1. 取得scrollLeft值: getScroll().left
2. 取得scrollTop值: getScroll().top

#### client系列
#### client系列的4个常用属性(clientTop和clientLeft这里不予介绍)
1. clientWidth : 获取网页可视区域的宽度

2. clientHeight: 获取网页可视区域的高度

3. clientX :获取鼠标事件发生时的应用客户端区域的水平坐标

4. clientY :获取鼠标事件发生时的应用客户端区域的垂直坐标
#### 兼容问题
(1) clientWidth 和 clientHeight的兼容问题
    //由浏览器对象不同导致

* 未声明 DTD: 谷歌,火狐,IE9+支持
```
document.body.clientWidth/clientHeight
```
* 已经声明DTD:IE8以下支持
```
document.documentElement.clientWidth/clientHeight
```
* 火狐/谷歌/ie9+以上支持的
```
 window.innerWidth/innerHeight
```
(2) clientWidth 和 clientHeight的兼容代码
```
function client(){
    if(window.innerWidth){
        return {
            "width":window.innerWidth,
            "height":window.innerHeight
        };
    }else if(document.compatMode === "CSS1Compat"){
        return {
            "width":document.documentElement.clientWidth,
            "height":document.documentElement.clientHeight
        };
    }else{
        return {
            "width":document.body.clientWidth,
            "height":document.body.clientHeight
        };
    }
}

```
 使用方法
 1. 取得clientWidth的值: client().width
 2. 取得clientHeight的值: client().height
(3)clientX 和 clientY的兼容问题
    //由事件参数对象的兼容性问题导致

1. 谷歌,火狐,IE9+: 事件参数对象随着事件处理函数的参数传入
2. IE8以下: event对象必须作为window对象的一个属性(window.event)
(4)clientX 和 clientY的兼容性代码
```
//将client和scroll的兼容问题进行对象的封装
    var evtTools={
        //获取兼容的事件参数对象
        getEvt:function (e) {
            return window.event?window.event:e;
        },
        //获取的是可视区域的横坐标
        getClientX:function (e) {
            return this.getEvt(e).clientX;
        },
        //获取的是可视区域的纵坐标
        getClientY:function (e) {
            return this.getEvt(e).clientY;
        },
        //获取向左卷曲出去的距离的横坐标
        getScrollLeft:function () {
            return window.pageXOffset||document.body.scrollLeft||document.documentElement.scrollLeft||0;
        },
        //获取向上卷曲出去的距离的纵坐标
        getScrollTop:function () {
            return window.pageYOffset||document.body.scrollTop||document.documentElement.scrollTop||0;
        }
    };

```
### 总结
网页可见区域宽： document.body.clientWidth;
网页可见区域高： document.body.clientHeight;
网页可见区域宽： document.body.offsetWidth   (包括边线的宽);
网页可见区域高： document.body.offsetHeight  (包括边线的宽);
网页正文全文宽： document.body.scrollWidth;
网页正文全文高： document.body.scrollHeight;
网页被卷去的高： document.body.scrollTop;
网页被卷去的左： document.body.scrollLeft;
网页正文部分上： window.screenTop;
网页正文部分左： window.screenLeft;
屏幕分辨率的高： window.screen.height;
屏幕分辨率的宽： window.screen.width;
屏幕可用工作区高度： window.screen.availHeight;
屏幕可用工作区宽度：window.screen.availWidth;


