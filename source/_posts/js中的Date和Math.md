---
title: js中的Date和Math
date: 2016-08-12
---
### Date对象
Date对象用于处理日期和时间
创建Date对象的语法：
``` bash
  var myDate=new Date()
```
注释：Date对象会自动把当前日期和时间保存为初始值。
#### Date对象属性
``` bash
  constructor   返回对创建此对象的Date函数的引用。
  prototype     使您有能力向对象添加属性和方法。
```
#### Date对象方法
这里列举出的是常用属性
1、Date() 返回当日的日期和时间。
2、getDate() 从 Date 对象返回一个月中的某一天 (1 ~ 31)。
3、getDay() 从 Date 对象返回一周中的某一天 (0 ~ 6)。
4、getMonth() 从 Date 对象返回月份 (0 ~ 11)。
5、getFullYear() 从 Date 对象以四位数字返回年份。
6、getHours() 返回 Date 对象的小时 (0 ~ 23)。
7、getMinutes() 返回 Date 对象的分钟 (0 ~ 59)。
8、getSeconds() 返回 Date 对象的秒数 (0 ~ 59)。
9、getMilliseconds() 返回 Date 对象的毫秒(0 ~ 999)。
10、getTime() 返回 1970 年 1 月 1 日至今的毫秒数。
11、setDate() 设置 Date 对象中月的某一天 (1 ~ 31)。
12、setMonth() 设置 Date 对象中月份 (0 ~ 11)。
13、setFullYear() 设置 Date 对象中的年份（四位数字）。
14、setHours() 设置 Date 对象中的小时 (0 ~ 23)。
15、setMinutes() 设置 Date 对象中的分钟 (0 ~ 59)。
16、setSeconds() 设置 Date 对象中的秒钟 (0 ~ 59)。
17、setMilliseconds() 设置 Date 对象中的毫秒 (0 ~ 999)。
18、setTime() 以毫秒设置 Date 对象。
19、toSource() 返回该对象的源代码。
20、toString() 把 Date 对象转换为字符串。
21、toTimeString() 把 Date 对象的时间部分转换为字符串。
22、toDateString() 把 Date 对象的日期部分转换为字符串。
### Math 对象
Math 对象用于执行数学任务。
使用 Math 的属性和方法的语法：
``` bash
  var pi_value=Math.PI;
  var sqrt_value=Math.sqrt(15);
```
注释：Math 对象并不像 Date 和 String 那样是对象的类，因此没有构造函数 Math()，像 Math.sin() 这样的函数只是函数，不是某个对象的方法。您无需创建它，通过把 Math 作为对象使用就可以调用其所有属性和方法。
#### Math 对象属性

``` bash
 1、E 返回算术常量 e，即自然对数的底数（约等于2.718）。 1
 2、 LN2 返回 2 的自然对数（约等于0.693）。
 3、LN10 返回 10 的自然对数（约等于2.302）。
  4、LOG2E 返回以 2 为底的 e 的对数（约等于 1.414）。 1
 5、LOG10E 返回以 10 为底的 e 的对数（约等于0.434）。
 6、PI 返回圆周率（约等于3.14159）。 1 3
 7、SQRT1_2 返回返回 2 的平方根的倒数（约等于 0.707）。
 8、SQRT2 返回 2 的平方根（约等于 1.414）。
```
#### Math 对象方法
1、abs(x) 返回数的绝对值。
2、acos(x) 返回数的反余弦值。
3、asin(x) 返回数的反正弦值。
4、atan(x) 以介于 -PI/2 与 PI/2 弧度之间的数值来返回 x 的反正切值。
5、atan2(y,x) 返回从 x 轴到点 (x,y) 的角度（介于 -PI/2 与 PI/2 弧度之间）。
6、ceil(x) 对数进行上舍入。
7、cos(x) 返回数的余弦。
8、exp(x) 返回 e 的指数。
9、floor(x) 对数进行下舍入。
10、log(x) 返回数的自然对数（底为e）。
11、max(x,y) 返回 x 和 y 中的最高值。
12、min(x,y) 返回 x 和 y 中的最低值。
13、pow(x,y) 返回 x 的 y 次幂。
14、random() 返回 0 ~ 1 之间的随机数。
15、round(x) 把数四舍五入为最接近的整数。
16、sin(x) 返回数的正弦。
17、sqrt(x) 返回数的平方根。
18、tan(x) 返回角的正切。
19、toSource() 返回该对象的源代码。
20、valueOf() 返回 Math 对象的原始值。

``` bash
 求x到y之间的任意随机整数
 Math.round(Math.random()*(y-x)+x)
```


