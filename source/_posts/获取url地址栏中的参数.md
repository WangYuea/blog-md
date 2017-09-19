---
title: 获取url中参数
---
有这样一个URL：http://item.taobao.com/item.htm?a=1&b=2&c=&d=xxx&e，请写一段JS程序提取URL中的各个GET参数(参数名和参数个数不确定)，将其按key-value形式返回到一个json结构中，如{a:’1′, b:’2′, c:”, d:’xxx’, e:undefined}
``` bash
 function getUrl() {
        var obj = {};
        var currentLink = window.location.href;
        var current = currentLink.indexOf('?');
        var category = currentLink.substr(current + 1);
        var str = category.split('&');
        for (var i = 0; i < str.length; i++) {
            var item = str[i];
            var items = str[i].split('=');
            obj[items[0]] = items[1];
        }
        return obj;
    }
```