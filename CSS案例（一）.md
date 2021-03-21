#### CSS案例（一）

导航页码

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .box a {
            display: inline-block;
            width: 36px;
            height: 36px;
            background-color: #f7f7f7;
            border: 1px solid #ccc;
            text-align: center;
            text-decoration: none;
            line-height: 36px;
            color: black;
        }
        
        .box .pre,
        .box .next {
            width: 85px;
        }
        
        .box .current {
            background-color: #fff;
            border: 1px solid transparent;
        }
    </style>
</head>

<body>
    <div class="box">
        <a href="" class="pre">&lt;&lt;上一页</a>
        <a href="">1</a>
        <a href="" class="current">2</a>
        <a href="">3</a>
        <a href="">4</a>
        <a href="">5</a>
        <a href="">6</a>
        <a href="">7</a>
        <a href="">8</a>
        <a href="" class="next">下一页&gt;&gt;</a>
    </div>
</body>

</html>
```

三角：

思路：盒子宽高为0，底部和左边框宽度为0，上边框宽度比右边框宽度大，即可得到一个直角三角形。

```html
<style>
    .box1{
        width: 0;
        height: 0;
        border-top: 100px solid transparent;
        border-right: 50px solid red;
        border-bottom: 0 solid transparent;
        border-left: 0 solid transparent;
    }
</style>
<body>
    <div class="box1">
        
    </div>
</body>
```

秒杀价格：

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .box1 {
            width: 0;
            height: 0;
            border-top: 100px solid transparent;
            border-right: 50px solid red;
            border-bottom: 0px solid pink;
            border-left: 0px solid skyblue;
        }
        
        .price {
            width: 160px;
            height: 24px;
            border: 1px solid red;
            margin: 0 auto;
            line-height: 24px;
        }
        
        .now {
            float: left;
            position: relative;
            width: 90px;
            height: 100%;
            background-color: red;
            text-align: center;
            color: #fff;
            font-weight: 700;
            margin-right: 8px;
        }
        
        .now i {
            position: absolute;
            width: 0;
            height: 0;
            right: 0;
            top: 0;
            border-color: transparent #fff transparent transparent;
            border-style: solid;
            border-width: 24px 10px 0 0;
        }
        
        .origin {
            color: rgb(175, 171, 175);
            text-decoration: line-through;
        }
    </style>
</head>

<body>
    <div class="box1">

    </div>
    <div class="price">
        <span class="now">￥1650<i></i></span>
        <span class="origin">￥5660</span>
    </div>
</body>

</html>
```

![2021-03-18_17-08-28.png](http://img.sinkcode.cn/2021/03/18/92fcd33d3d0ed.png)