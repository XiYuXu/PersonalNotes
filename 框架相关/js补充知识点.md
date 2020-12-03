1.模板字面量
相当于格式化字符串,字符串用两个``包含起来,并且内部的占位符用${variable}标识.一般用于标识多行文本或者配合函数使用.

2.forEach与箭头函数
forEach用于数组,是用于让数组每一个元素都调用函数的语法,基本格式为function(currentValue,index,arr)),其中index为数组元素下标,arr为当前元素所属的数组对象.
在实际调用时只需要onclick = "array.forEach(function)"

箭头函数:对于匿名函数,函数参数,语句和返回值才是有价值的部分,只是对原有定义方式的简写.

上述两知识点混合例子:
// ES6
nums.forEach(v => {
	if (v % 5 === 0)
		fives.push(v);
})

// ES5
nums.forEach(function (v) {
	if (v % 5 === 0)
		five.push(v);
})

3.用获取css样式表中指定选择器函数 doument.querySelector("#demo");参数与css选择器语法类似,
该函数只返回第一个元素,要想返回全体选择器,代替使用querySelectorAll(".demo")

js构造函数不需要return
functoin Create_Object(x,y){
	this.x = x;
	this.y = y;
	//无需return
}
var object = new Create_Object(1,1);
为对象添加一个函数属性,则用
Object.prototype.functionName = function(){

}
调用时便object.functionName

prototype看作类的定义,而在类的实例中添加的属性或函数不影响原型,继承时要是想继承父类的东西,它的东西必须放在构造器中或者(放到prototype中然后son.prototype = father.prototype).

若是想要指定一个对象的prototype指向另一个对象的prototype,但是没有继承机制,那么构造函数中的方法不可用,但是prototype中的方法可用

array.forEach(function(currentValue,index,array){
	...
};
currentValue必须有表示数组元素值,index为索引值,array为数组对象.

stream是一个event的实例,所以在使用流时可以为其添加监听器.如 
var data;
fileStream=fs.createReadStream(path,'utf-8');
fileStream.on('data',function(chunk){
	data+=chunk;
})
														