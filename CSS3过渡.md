#### CSS3过渡

`trasition: attribution time cursor how;`

分别是

1. 过渡属性，如果想要所有属性都变，设置`all`
2. 过渡时间，单位为s秒
3. 曲线，默认是ease
4. 何时开始（延迟时间）

**使用原则**：谁使用给谁加

```html
<style>
        .transition {
            width: 100px;
            height: 50px;
            background-color: skyblue;
            transition: width .5s;
        }
        
        .transition:hover {
            width: 200px;
        }
  </style>
<body>
    <div class="transition">

    </div>
</body>
```

