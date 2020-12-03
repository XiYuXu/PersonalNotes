title: css基础知识点
---

text-decoration:none;		//取消线的格式
text-decoration:line-throuth;		//穿越线
text-decoration:overline;		//上划线
text-decoration:underline;		//下划线

///指定文本大小写///
text-transform: uppercase;		
text-transform: lowercase;

text-indent:50px; 			//指示文本缩进
letter-spacing:2px;			//指定文字间隔大小
word-spacing:20px;			//指定单词间隔大小
white-space:nowrap;		//禁用一个元素内的文字环绕
line-height:70%;			//指定行高
direction:rtl;			//指定文本显示方向,注意不要引号
text-shadow:2px 2px #ff0000;		//设置文本阴影

/*字体样式*/
font-style:normal;
font-style:italic;
font-size:1em; 			//1em等于16px大小
font-weight:bold;			//加粗,相关属性有lighter.normal
font:bold italic 12px/30px Georgia,Serif;

/*列表样式*/
list-style-type: square;		//无序,表示方框,相关属性值有circle
list-style-type:upper-roman;		//有序,表示大写罗马符号,lower-alpha
list-style-image

/*表格样式*/
border-collapse:collapse;		//表示表格td,th边框与table边框叠加

border-style有如下值:dotted dashed double groove 

轮廓outline:指定形式 颜色和宽度

隐藏一个元素可以通过把display属性设置为"none"，或把visibility属性设置为"hidden"。但是请注意，这两种方法会产生不同的结果。

visibility:hidden可以隐藏某个元素，但隐藏的元素仍需占用与未隐藏之前一样的空间。也就是说，该元素虽然被隐藏了，但仍然会影响布局。

让元素居中对齐,则先要设置该元素的宽度,再加上 margin:auto;
让图片居中对齐,则先设置图片的样式为block,再使用margin:auto;{display:block; margin:auto}

position定位:
relative:相对element在文档中原来的位置
absolute:完全脱离文档流,具体相对对象由定位上下文决定.
fixed:  相对浏览器窗口定位
只有一个元素被标记为sticky,relaitive,absolute而不是static它的属性值left right等才起作用.与父元素共享起点.
设置父元素为relative,子元素为absolute,则子元素的上下文为父元素.

