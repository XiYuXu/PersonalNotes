### 模板字面量
相当于格式化字符串,字符串用两个``包含起来,并且内部的占位符用${variable}标识.一般用于标识多行文本或者配合函数使用.

### forEach与箭头函数
forEach用于数组,是用于让数组每一个元素都调用函数的语法,基本格式为function(currentValue,index,arr),其中index为数组元素下标,arr为当前元素所属的数组对象.
在实际调用时只需要onclick = array.forEach( ()=>{} )

### 箭头函数
对于匿名函数,函数参数、语句和返回值才是有价值的部分,只是对原有定义方式的简写.

上述两知识点混合例子:
```
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
```

获取css样式表中指定选择器函数
**doument.querySelector("#demo");**
参数与css选择器语法类似,
该函数只返回第一个元素,要想返回全体选择器,代替使用querySelectorAll(".demo")

stream是一个event的实例,所以在使用流时可以为其添加监听器.如 
var data;
fileStream=fs.createReadStream(path,'utf-8');
fileStream.on('data',function(chunk){
	data+=chunk;
})
														