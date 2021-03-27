#### CSS transform

可以实现元素的位移(translate)、旋转(rotate)、缩放(scale)等效果。

##### translate

改变元素在页面中的位置，不会影响到其他元素，类似定位。用法：`transform: translate(x, y);`

如果只移动X或Y，可以使用：`transform: translateX(n)`或者`transform: translateY(n)`,需要注意的是该属性对**行内标签**没有效果。

* 如果是百分比，则该百分比是针对自身的百分比。

##### rotate

这个属性就是让元素在2维平面内旋转，用法：`transform: rotate();`，单位是deg。

###### 设置旋转中心点

可以使用`transform-origin: x y;`来设置，可以使用方位名词

##### 缩放scale

语法：`transform: scale(x, y);`，里面写的是数字，没有单位，小于1就是缩放。

* 优点：对比直接修改宽高，缩放不会影响其他元素。而且可以设置缩放的中心点。

*`transform`*属性的书写顺序会影响最终的效果，一般把`translate`放在最前面。