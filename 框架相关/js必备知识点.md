##js的三种调用方式##
嵌入到<head>中
js类似java,一切皆<b>对象</b>.
js基本数据类型:<b>数值型 字符串 布尔型 null undefined</b>
对象类型:<b>数组 普通对象 Date RegExp</b>
对象是<b>键值对</b>的集合 用{}括起来,类似
'''
{x:1,y:2,z:3,play:function(){alert("nimei");}}
'''
数组也是一个对象用[]表达,类似[1,2,3]

允许变量自适应类型甚至重名定义,如:
'''
    var a=6;
    a=false;
    var a="nimei";
'''

##js中的等号:
<b>==</b>
只比较值,忽略数据类型
<b>===</b>
先比较数据类型,再比较值

##逻辑运算符&& ||  !
运算结果不一定是bool值
如短路算法:var result=a||b, 若是a有值则为a,若是a为null或undefined,result = b.

var a=number("100px");得到NAN
var a=parseInt("100px");得到100

