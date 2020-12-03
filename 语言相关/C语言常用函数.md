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

