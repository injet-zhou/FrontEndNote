#### CSS初始化(CSS reset)

CSS初始化就是把浏览器的默认样式重置，比如`<li>`标签一般是不需要前面的远点的，这时候就需要在开始的时候将其设置为`list-style: none;`

常用的初始化代码：

```css
*{
    padding: 0;
    margin: 0;
}
li{
    list-style: none;
}
img{
    // 照顾低版本浏览器，如果图片外面包含了链接会有边框的问题
    border: 0;
    // 取消图片底侧有空白问题
    vertical-align: middle;
}
button{
    cursor: pointer;
}
a{
    text-dercoration: none;
}
body{
    font-family: "\5B8B\4F53" // 宋体的Unicode
}
```



