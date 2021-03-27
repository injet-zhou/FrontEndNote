#### CSS3盒子模型

##### border-box

盒子大小:`width`，padding和border不会撑大盒子。

##### content-box(默认)

盒子大小为`width+padding+border`

```html
<style>
        .content-box {
            width: 200px;
            height: 200px;
            background-color: pink;
            border: 20px solid red;
            padding: 15px;
        }
        
        .border-box {
            box-sizing: border-box;
            width: 200px;
            height: 200px;
            background-color: pink;
            border: 20px solid red;
            padding: 50px;
        }
</style>

<div class="content-box">我是content-box</div>
<div class="border-box">我是border-box</div>
```



![border-box.png](http://img.sinkcode.cn/2021/03/26/9a57148b7cdfb.png)