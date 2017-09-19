---
title: b继承a的方法
---
就是利用的了call和apply的方法实现了继承。
``` bash
function A( age, name ){
    this.age = age;
    this.name = name;
}

A.prototype.show = function(){
    alert('父级方法');
}

function B(age,name,job){
    A.apply( this, arguments );
    this.job = job;
}

B.prototype = new A();
var b = new A(14,'侠客行');
var a = new B(15,'狼侠','侠客');
console.log(b);//age: 14, name: "侠客行"
console.log(a);//age: 15, name: "狼侠", job: "侠客"

```