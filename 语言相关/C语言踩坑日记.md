#### 指针传参问题

> 即便传入的是一个指针，由于c语言没有提供引用传递的机制，还是会给参数分配新的空间，所以还是要用返回值

#### fgets读取一行文件时取不出内容

> 读取一行内容必须是用数组读取，用字符串指针填充不了内容

#### 把字符串赋值给指针，不会自动添加\0

```c
char *p=(char *)malloc(100)

p="fdasfs"
```

#### strcpy第一个参数不能是NULL

> 所以要先申请空间

