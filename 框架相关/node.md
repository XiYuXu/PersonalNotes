##Node js基础:
<hr/>

1. 每一种解析器都是一个运行环境，不但允许JS定义各种数据结构，进行各种计算，还允许JS使用运行环境提供的内置对象和方法做一些事情。例如运行在浏览器中的JS的用途是操作DOM，浏览器就提供了document之类的内置对象。而运行在NodeJS中的JS的用途是操作磁盘文件或搭建HTTP服务器，NodeJS就相应提供了fs、http等内置对象。

2. node中有三种关于模块的东西, exports与module**对象**,require**函数**.

3. require用于加载已经存在的一个模块,返回的是一个模块对象. 如: var module1=require("./foo.js");
exports常用于导出模块公有方法和属性,别的模块通过require引入当前模块得到的就是一个exports对象,如:
```
    exports.hello=function(){
        console.log("nimei");
    }
```
4. module对象表示的是当前模块的一些信息,通常用于操作当前模块的导出对象,例如本来exports默认是一个普通对象,导出对象更换为函数操作如:
```
    module.exports=function(){
       console.log("nimei");
    }
```
5. 使用node script.js命令后该模块只执行**一次**,然后其导出对象被缓存起来,后续重复利用,像极了C语言中的静态变量.
<br>

##Node代码的组织和部署
<hr/>

**一.模块路径解析规则**:除了支持一般的绝对路径和相对路径之外(由./或者/或者../开头路径),require函数支持第三种形式的路径，写法类似于foo/bar,以下排列反映优先级.
   1. 内置模块(也就是先找本地目录) :
   如果传递给require函数的是NodeJS内置模块名称，不做路径解析，直接返回内部模块的导出对象，例如require('fs')。
   2. node_modules目录:
    如果模块不是以 '/', './' 或 '../' 开头的，那么 node 会从当前模块的父目录开始，尝试在它的 node_modules 文件夹里加载相应模块,node_modules目录用于存放模块。例如某个模块的绝对路径是/home/user/hello.js，在该模块中使用require('foo/bar')方式加载模块时，则NodeJS依次尝试使用以下路径:
   >/home/user/node_modules/foo/bar
    /home/node_modules/foo/bar
    /node_modules/foo/bar
   
   3. NODE_PATH环境变量:
      与PATH环境变量类似，NodeJS允许通过NODE_PATH环境变量来指定额外的模块搜索路径。NODE_PATH环境变量中包含一到多个目录路径，路径之间在Linux下使用:分隔，在Windows下使用;分隔。例如定义了以下NODE_PATH环境变量：
   >NODE_PATH=/home/user/lib:/home/lib

**二. 包管理**
复杂些的模块往往由多个子模块组成。为了便于管理和使用，我们可以把由多个子模块组成的大模块称做包，并把所有子模块放在同一个目录里。

在组成一个包的所有子模块中，需要有一个入口模块，入口模块的导出对象被作为包的导出对象。也就是一个集线器而已.
想自定义入口模块的文件名和存放位置，就需要在包目录下包含一个package.json文件，并在其中指定入口模块的路径。如下:
```
- /home/user/lib/
    - cat/
        + doc/
        - lib/
            head.js
            body.js
            main.js
        + tests/
        package.json
```
其中package.json内容如下。
```
{
    "name": "cat",
    "main": "./lib/main.js"
}
```
如此一来，就同样可以使用require('/home/user/lib/cat')的方式加载模块。NodeJS会根据包目录下的package.json找到入口模块所在位置。

三.目录结构
除了代码外，一个完整的程序也应该有自己的文档和测试用例。因此，一个标准的工程目录都看起来像下边这样。
>- /home/user/workspace/node-echo/   # 工程目录
    - bin/                          # 存放命令行相关代码
        node-echo
    + doc/                          # 存放文档
    - lib/                          # 存放API相关代码
        echo.js
    - node_modules/                 # 存放三方包
        + argv/
    + tests/                        # 存放测试用例
    package.json                    # 元数据文件
    README.md                       # 说明文件

    