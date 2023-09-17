> 注：只能采用文本文件格式
> fprintf(FILE *fp,char *format);
> fscanf(FILE *fp,char *format)

>  注：只能采用二进制文件格式
> int fread(void *buffer, int size, int count, FILE *stream)
> int fwrite(void *buffer, int size, int count, FILE *stream)



#### 连接字符串

```
concat(char *,char *q) //返回连接后的值，第一个参数的值也会改变为连接值
```

#### 分割字符串

```c
char tempString[60]= "abc,d,e,f";
p=strtok(tempString,",");
while(1){
    if(p!=NULL){
	    printf("%s\n",p);
        p=strtok(tempString,",");
    }
    else
        break;
}
```
#### 找某个字符
```
char* strchr(char const *str,int ch); //返回指向第一个ch出现的位置的指针
char* strrchr(char const *str,int ch);//返回指向最后一个ch出现位置的指针，r代表right
```
#### 匹配某些字符
```
char* strbrk(char const *str,char const *group); //返回指向group字符序列中第一次出现元素位置
```

#### 找子字符串
``` 
char* strstr(char const *s1,char const *s2); //返回指向s2第一次出现在s1中的位置
```
#### 分割字符串
```
char *strtok(char *str,char const *sep);
```