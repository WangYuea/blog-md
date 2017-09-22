---
title: javasccript中的类型转换
date: 2016-08-05
---
### 字符串类型转换
三种换转方式，toString 、String 、隐式转换
``` bash
 1、toString()可以转换数值、布尔、数组、对象，但是undefined和null不可以转化，undefined和null没有toString()方法。
 2、String() 都可以转换，包括undefined和null，undefined转换成undefined，null转换成null。
 3、隐式转换，用加好拼接，1和2是强制转换。
```
### 数值类型转换
三种换转方式，Number 、parseInt（parseFloat） 、隐式转换
``` bash
 1、Number()转不了的就是NaN，空字符串返回0
 2、parseInt()转换成整数，parseFloat()转换成小数。
 3、隐式转换，用减、乘、除，1和2是强制转换。
```
### 布尔类型转换
``` bash
    数值类型    字符串类型   布尔类型   undefined   null   object
真  非0数字     非空字符串    true                          object

假   0           空字符串     false      undefined   null
```
Boolean()凡是对象都为真，不管有无内容
取反！！ 隐式转换
