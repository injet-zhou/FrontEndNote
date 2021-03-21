#### 清除浮动

##### 为什么清除浮动

前面的笔记中的父盒子是标准流且有高度，但是有时候父盒子的高度是无法获知的。这显然是满足不了需求的（不设置父盒子高度，子盒子浮动，这时候子盒子脱离标准流，父盒子没有内容了，高度就自动变成0，后面的内容就会“补”上来，出现意料之外的效果），这时候就要清除浮动了。

##### 清除浮动的本质

本质是清除浮动元素造成的影响（触发[BFC](https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Block_formatting_context),Block Format Context)。清除浮动之后，父盒子自动检测子盒子的高度，父级盒子这时候就有了高度。

##### 如何清除

用`clear: right | left | both;`来清除：

| right          | 清除左侧浮动的影响     |
| -------------- | ---------------------- |
| left           | 清除右侧浮动的影响     |
| both(**常用**) | 清除左右两侧浮动的影响 |

清除浮动的策略：**闭合浮动**

###### 方法

1. **额外标签法**，也称隔墙法，W3C推荐做法，在最后的子元素后面添加额外的标签，并给额外的标签添加`clear: both;`，额外的标签**必须是块级元素**。

2. 父级添加overflow属性，设置为hidden、auto或者scroll。缺点是溢出的部分不可见。

3. 父级添加after伪元素(本质上像额外标签法给最后加一个盒子)

   ```css
   .clearfix:after{
       content: "";
       display: block;
       height: 0;
       clear: both;
       visibility: hidden;
   }
   .clearfix {
       /* IE7、6专有 */
       *zoom: 1;
   }
   ```

   

4. 父级添加双伪元素

   ```css
   .clearfix:before,.clearfix:after{
       content: "";
       display: table;
   }
   .clearfix:after{
       clear: both;
   }
   .clearfix {
       /* IE7、6专有 */
       *zoom: 1;
   }
   ```

   伪元素要兼容IE。