#### SEO优化

SEO的字面意思是搜索引擎优化，提升在搜索引擎页面的排名。

页面必须有三个标签来符合SEO优化：title、description、keyword

##### title

具有不可替代性，是非常**重要**的标签，是搜索引擎了解网页的入口和网页主题归属的最佳判断点。

##### description

简要说明网站主要是做什么的，主要用法：

`<meta name="description" content="xxxxxx">`

##### keywords

关键词也是搜索引擎的关注点之一。`<meta name="keywords" content="xxxx">`

##### LOGO SEO

1. logo里面首先放一个`<h1>`标签，目的是为了提权，告诉搜索引擎，这个地方很重要。
2. `<h1>`里面再放一个**链接**，可以返回首页
3. 链接里面要放文字（网站名称），但是文字不显示
   - 方法一：`text-indent`移到盒子外面，如`text-indent: 9999px;`，然后`overflow: hidden;`
   - 方法二：直接给`font-size: 0`，就看不到文字了
4. 最后给链接一个`title`属性，这样鼠标放到logo上就可以看到提示文字了。