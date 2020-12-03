使用 data-* 为元素嵌入自定义属性,这样在关联某些元素时可以通过指定相同自定义属性实现
语法: <element data-*="somevalue">,其中*标识一个或多个字符,且不允许大写.

若是想将整张图片作为页面背景,可编辑如下css:
html
{
    background: url(https://www.baidu.com) bottom center;        //url不需要""包围
    background-size:cover;
}

transform:scale(1.1);   //扩大至1.1倍

[Flex布局](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html):

rem是html的font-size的倍数单位,若设置html的font-size为10px,则1.5rem为15px.

.keys {             //使得.keys元素在浏览器窗口内水平垂直居中
    display: flex;
    flex: 1;
    min-height: 100vh;  //必须包含视窗高度,不加则默认在纵轴向上对齐.
    align-items: center;
    justify-content: center;
}