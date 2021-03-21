#### CSS技巧

##### 雪碧图

为了提高页面加载速度，减少请求与响应次数，出现了**雪碧图**，雪碧图是将多张图片”合并“在一张图片中。

##### 雪碧图的特点

1. 主要针对背景图片使用，把多张背景小图片整合到一张大图片中。
2. 移动图片位置时使用`background-position`设置。

##### 鼠标不可用样式

`cursor: not-allowed;`

##### 防止文本域拖拽

`textarea { resize: none;}`

##### 垂直居中

此方法只适用于**行内块**或者**行内元素**，使用`vertical-align: middle;`，默认是baseline;

##### 解决图片底部有空白缝隙

使用`vertical-align`设置只要不是baseline就行，产生这个问题的原因就是baseline对齐造成的。