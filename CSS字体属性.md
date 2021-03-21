#### CSS字体属性

##### font-weight

设置文本的字体粗细，属性值可用英语表示，也可用数字

如normal是正常字体粗细，bold是加粗，对应的数值为400和700，实际开发常用**数字**表示。

##### font-style

可设置字体是否倾斜，默认是normal，当属性值为italic时是斜的，代表书写体，而oblique表示的是常规字体的倾斜形式，可设置倾斜度，格式为`font-style: oblique 40deg;`，表示倾斜40度。如果当前字体没有italic(斜体)版本，则会选用oblique(倾斜)版本，反之则亦然。

##### text-align对齐文本

用于设置文本的水平对齐方式，如`text-align: center;`居中对齐。

##### text-decoration文本装饰

可设置下划线等效果。

| underline    | 下划线 |
| ------------ | ------ |
| overline     | 上划线 |
| line-through | 删除线 |

##### text-intent文字缩进

`text-intent`可用来设置段落首行的缩进，格式为`text-intent: 20px;`，按照中文习惯，一般段落首行缩进两个文字，此时可以用`text-intent: 2em;`，其中em是相对单位，表示当前元素一个文字的大小，所以无论文字的`font-size`有多大，都是缩进两个文字。

##### line-height行间距

用来设置行间的距离，一般是指文字的上间距和下间距，比如`line-height: 26px;`，当字体大小为16时，上间距和下间距分别为5px。