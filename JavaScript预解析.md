#### JavaScript预解析

先看一段代码：

```js
console.log(num);
var num = 10;
```

那么输出结果是什么呢？结果是undefined，为什么是这样呢？

这就涉及到JavaScript引擎执行的过程了，JavaScript执行的过程分为两步：**预解析**和**代码执行**。

##### 预解析

JavaScript会把代码里面的所有var声明的变量还有function提升到当前作用域的最前面。

###### 变量预解析

变量提升只把所有变量提升到当前作用域的最前面，不进行赋值操作。这就能解释前面的代码结果为什么是undefined。

###### 函数预解析

把函数声明提到前面，但是没有调用。

```js
func();
var func = function(){
    console.log("Hello"); // 报错
}
```

上面这段代码相当于：

```js
var func;
func();
func = function(){
    console.log("Hello")
}
```



##### 代码执行

先进行预解析，再按照书写的顺序从上到下执行。

案例1：

```js
var num = 10;
fun();
function fun(){
    console.log(num);
    var num = 20;
}

// 相当于以下代码:
var num;
function fun(){
    var num;
    console.log(num); // 输出undefined
    num = 20;
}
num = 10;
fun();
```

案例2：

```js
var num = 10;
function fn(){
    console.log(num);
    var num = 20;
    console.log(num);
}
fn();

// 实际上相当于以下代码：
var num;
function fn(){
    var num;
    console.log(num); // 输出undefined
    num = 20;
    console.log(num); // 输出20
}
num = 10;
fn();
```

案例3：

```js
var a = 18;
f1();
function f1(){
    var b = 9;
    console.log(a);
    console.log(b);
    var a = '123';
}

// 实际上相当于以下代码
var a;
function f1(){
    var b;
    var a;
    b = 9;
    console.log(a); // 输出undefined
    console.log(b); // 输出9
    a = '123';
}
a = 18;
f1();
```

案例4：

```js
f1();
console.log(c);
console.log(b);
console.log(a);

function f1(){
    var a = b = c = 9;
    // 相当于var a = 9; b = 9; c = 9;
    console.log(a);
	console.log(b);
	console.log(c);
}

// 相当于以下代码：
function f1(){
    var a;
    a = b = c = 9;
    // 相当于var a = 9; b = 9; c = 9;
    // 不是 var a; var b; var c;
    // 说明b,c是全局变量
    console.log(a); // 输出9
	console.log(b); // 输出9
	console.log(c); // 输出9
}
f1();
console.log(c); // 输出9
console.log(b); // 输出9
console.log(a); // 报错
```

