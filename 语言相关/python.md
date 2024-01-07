### 常用字符串库函数
```
'hello'.title()   //Hello
'hello'.upper()   //HELLO
'HELLO'.lower()   //hello

lastName = 'Hello   '
firstName = '   World'
string = f'{lastName.rstrip()} {firstName.lstrip()}' //Hello World   去空格

name = "hello world"
name.split()        //['hello', 'world']
name                //"hello world"
```

### f(format)模板字符串
```
lastName = 'Hello'
firstName = 'World'
f'{lastName} {firstName}'  //Hello World
```

### 同时赋值
```
x,y,z = 0,0,0
```

### python列表和数组不同的地方
```
# 添加
list.append(element)       //添加元素
list.insert(index,element) //指定位置插入元素

# 删除
del list[4]                     //删除元素
lastElement = list.pop()        //获得列表尾元素并出列表
someElement = list.pop(index)   //删除任意位置元素
list.remove(someElementValue)   //根据值删除,只删除第一次碰到的

#排序
# 修改原数组
list.sort()                 //从小到大
list.sort(reverse=true)     //从大到小
# 不修改原数组
sorted(list)

# 列表反转
list.reverse()

# 获取列表长度
len(list)

#获取最后一个元素
list[-1]                    //其实-2，-3，-4也行
```

### 数字列表
```
#注意一个list变量不能重新指定新的类型，所以同时执行下面两条语句是错的
list = range(1,5)  //包含1，2，3，4的range 若直接打印为range(1,5)
list = list(range(1,5)) //把range改为list，打印为[1,2,3,4]


#指定步长
list = range(1,5,2) //涉及1，3

#找最大、最小值、求和
sum(numList)
min(numList)
max(numList)

#用循环及列表解构的方式 创建数字列表
list = [element**2 for element in range(1,4)]   //把循环体中元素的返回值放最前，循环头放后面
```

### 切割列表
```
list = list(range(1,6)) //[1,2,3,4,5]
list[0,3]               //[1,2,3]
```

### 循环
```
# for in循环
for element in list:   #注意有个冒号
    print(element)     
print(element)         #循环结束后，element依然生效
```

### 遍历字典
```
for key,value in list.items()  //遍历键值对
for key in list.keys()         //遍历键值
for value in list.values()         //遍历值
```

