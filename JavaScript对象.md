#### JavaScript对象

##### 什么是对象

在JavaScript中，对象是一组无序的相关属性和方法的组合。在JavaScript的概念中，一切皆对象。

##### 对象的创建

###### 使用字面量

```js
var person = {
    // key: value 的形式，并用','隔开
    pname: "法外狂徒张三",
    gender: "男",
    eat: function(){
        console.log("吃饭");
    }
}
// 使用'.'来使用器属性
console.log(person.pname);
// 或者使用obj['attribute']
console.log(person['pname'])
```

##### 使用new关键字

```js
var obj = new Object();
obj.uname = "张三"; // OK
obj['age'] = 20; // OK
```

##### 使用构造函数

以上两种方法如果创建的对象一多，代码就会臃肿，复用性不高，构造函数就是把对象里面一些相同的属性和方法抽象出来。格式如下：

```js
function ConstructorName(args){
    this.attribute = value;
    this.Function = function(){}
}
// 实例化一个对象
new ConstructorName(args);
```

###### 构造函数构造对象的过程

1. new构造函数在内存中创造一个空对象
2. this就会指向刚才创建的对象
3. 执行构造函数里面的代码，给对象添加属性和方法
4. 返回这个对象