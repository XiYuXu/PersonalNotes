## js中的等号:
<b>==</b>
只比较值,忽略数据类型
<b>===</b>
先比较数据类型,再比较值

# #逻辑运算符&& ||  !
运算结果不一定是bool值
如短路算法:var result=a||b, 若是a有值则为a,若是a为null或undefined,result = b.

var a=number("100px");得到NAN
var a=parseInt("100px");得到100

