#### CSS背景

##### 背景颜色

可用`background-color`进行设置，默认值为transparent，即透明。

##### 背景图片

可用`background-image`进行设置，可用于LOGO等，属性值需要用`url()`进行设置。

##### 背景平铺

如果盒子大小比背景图片大，就会出现背景图片重复平铺的效果，此时可用`background-repeat`来设置背景平铺的效果，比如不平铺、沿着某一条轴平铺等。

##### 背景图片位置

可用`background-position`来设置图片在背景中的位置，格式为`background-position: x y;`，既可以用坐标的形式，也可以用center、left等方位名词，此时xy的顺序对效果没有影响，如left top和top left效果是一样的。如果只有一个方位名词，另一个则默认居中。

单位也可以用混合单位，比如`background-position: 20px center;`。

##### 背景图像固定

背景图像固定的意思是当滚动时背景是跟着滚动还是固定不懂，可用`background-attachment`进行设置，属性值有scroll和fixed两个值，分别是跟着滚动和不滚动。