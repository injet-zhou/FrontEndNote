#### CSS动画

animation可以实现更复杂的动画效果。制作动画的步骤：

1. 定义动画
2. 使用（调用）动画

##### keyframes定义动画

```css
@keyframes animationName {
    /* 0%、100%为动画序列 */
    /* 0%为开始状态 */
    0% {
        width: 100px;
    }
    /* 100%为结束状态 */
    100% {
        width: 200px;
    }
}
```

动画序列也可以用`from`和`to`，百分比是`animation-duration`的百分比。

##### 元素使用动画

```css
.box{
    animation-name: 动画名字;
    animation-duration: 持续时间;
}
```

