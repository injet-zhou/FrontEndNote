#### JavaScript作用域

##### 什么是作用域

就是代码名字在某个范围内起作用和效果，目的是为了提高程序的可靠性，这只是大的方向，最直接的就是减少命名冲突

全局作用域：整个`<script>`标签

局部作用域：函数内部就是局部作用域。局部作用域的变量和全局作用域的变量不影响。

```js
var num = 20;
console.log(num); // 输出结果: 20
function fn(){
    var num = 10;
    console.log(num);
}
fn(); // 输出结果：10
```

**注意**：在函数里面直接赋值，但没有声明变量，该变量会被认作全局变量。

```js
function fun(){
    num = 20;
}
console.log(num); // 输出结果：20
```

##### 全局变量和局部变量

1. 全局变量只有浏览器关闭时才会销毁，比较占内存资源。
2. 局部变量当程序执行完毕就会销毁，不浪费内存资源。

JavaScript没有块级作用域（ES6才有）

##### 作用域链

一个函数里面可以声明函数，同时内部函数可以访问外部函数的变量，通过链式查找决定使用哪个函数，内部->外部->全局（就近原则）。

```js
var num = 10;
function fn(){
    var num = 20;
    function func(){
        console.log(num); // 输出：20
    }
}
```

案例：

```js
function f1(){
    var num = 123;
    function f2(){
        console.log(num);
    }
    f2();
}
var num = 456;
f1();
```

输出：123