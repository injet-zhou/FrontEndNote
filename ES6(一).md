#### ES6(一)

##### Const常量

1. 必须赋初值

2. 常量值无法修改

3. 块级作用域

   ```js
   {
       const age = 12;
   }
   console.log(age) //报错
   ```

4. 对数组或对象的元素修改，**不算**做对常量的修改（常量的地址没有改变）

##### 解构赋值

数组解构

```js
const F4 = ['小沈阳','刘能','赵四','宋小宝']
let [xiao,liu,zhao,song] = F4;
console.log(xiao); // 输出：小沈阳
```

对象解构

```js
const zhaobenshan={
    name: '赵本山',
    age:45,
    perform: function(){
        console.log("小品");
    }     
}
let {perform} = zhao;
perform(); // 输出：小品
```

##### 模板字符串

```js
let str = "解构";
let p = "你了解`str`吗？";
console.log(p); // 输出：你了解解构吗？ 
```

##### 对象简化

```js
let name = "sinkcode";
let change = function(){
    console.log("we are family");
}
// 原来的
const blog = {
    name: name,
    change: change,
    comment: function(){}
}
// 简化
const blog = {
    name,
    change,
    comment(){}
}
```

##### 箭头函数

1. this是静态的，始终指向函数声明时所在的作用域下的this值

```js
// 传统
let fn = function(){
    console.log("hello");
}
// 箭头函数
let fn = ()=>{
    console.log("hello");
}
```

##### 函数参数默认值

有默认值的参数一半要放后面。

```js
function add(a,b,c=10){
    return a+b+c;
}
let result = add(1,2);
console.log(result); // 输出：13
```

可以和解构赋值搭配使用

```js
// ES6以前
function connect(options){
    console.log(options.host);
    console.log(options.username);
}
connect({host: 'localhost','su'});

// ES6
function connect({host,username}){
    console.log(host);
    console.log(username);
}
```

##### rest参数

```js
// ES5获取实参的方法
function get(){
    console.log(arguments); // 输出一个对象
}
get("川建国","希腊里");

// ES6 rest参数
function done(...args){
    console.log(args); // args是一个数组
}
done("麻辣香锅", "猪肚鸡");
```

##### 扩展元素符

'...' 扩展运算符能将数组转换为','分割的**参数序列**。

```js
const phone = ['Apple','Android',"Windowphone"]
function get(){
    console.log(arguments);
}
get(...phone); // 输出'Apple','Android',"Windowphone"

const ChinaBrands = ['Xiaomi',"Vivo","Huawei","Oppo"];
const ForeignBrands = ['Apple','Samsung','Google'];
const Brands = [...ChinaBrands,...ForeignBrands]
console.log(Brands); //输出['Xiaomi',"Vivo","Huawei","Oppo",'Apple','Samsung','Google']
```

##### Symbol数据类型（原始）

Symbol表示独一无二的值，用来解决命名冲突的问题，且不能和其他数据进行运算，也不能用for...in循环来遍历，可用**Reflect.ownKeys**来获取对象的键名。

```js
let person1 = Symbol("张三"); // 注意没有new，因为在ES6中，从基本类型创建一个简单包装类型已经被废弃，但是Boolean等由于遗留原因仍然可用
let person2 = Symbol("张三");

console.log(person1 === person2); // false

let name1 = Symbol.for("李四");
let name2 = Symbol.for("李四");

console.log(name1 === name2); // true
```

##### 迭代器(iterator)

是一种接口，为各种不同的数据解构提供统一的访问接口。任何数据解构只要部署iterator接口（对象的一个属性），就可以完成遍历操作。ES6创造了一种新的遍历命令for...of循环，iterator接口主要供for...of消费。

```js
const ChinaBrands = ['Xiaomi',"Vivo","Huawei","Oppo"];
for(let b of ChinaBrands){
    console.log(b); //分别输出'Xiaomi',"Vivo","Huawei","Oppo"
}
```

自定义遍历数组

```js
const banji = {
    name: "三年二班",
    students: ['king','giao','wdnmd','yaoshuige'],
    [Symbol.iterator](){
        let index = 0;
        let _this = this;
        return {
            next: function(){
                if(index<_this.students.length){
                    const result = {value: _this.students[index],done: false}
                    index++;
                }
                else{
                    return {value: undefined,done: true}
                }
            }
        }
    }
}

for(let b in banji){
    console.log(b); // 依次输出students数组里面的值
}
```

##### 生成器

传统的异步编程使用纯回调函数，生成器就是新增的用来异步编程的特殊函数

```js
function * gen(){
    console.log("I am generator");
}
let iterator = gen();
console.log(iterator); // 输出一个对象
iterator.next(); // 输出'I am generator'

// 生成器函数可以使用yield语句，是函数代码的分割符
function * gen(){
    console.log("一鞭");
    yield '很快啊';
    console.log("两鞭");
    yield '啪的一下';
    console.log("三鞭");
    yield '我大E了';
    console.log("四鞭");
}
```

![2021-03-17_23-57-40.png](http://img.sinkcode.cn/2021/03/17/0196d2be85463.png)