#### 实现插入的数据主键自增的触发器

```sql
CREATE TRIGGER TriggerName 
BEFORE INSERT ON TableName
FOR EACH ROW
BEGIN
	set new.id=(
		select id+1 from user 
		ORDER BY id desc
		LIMIT 1
	);
END
```

#### 当查询的数据中包含聚集函数时，取某一行的值是不可靠的

```sql
SELECT name, LENGTH(name)
FROM user 
ORDER BY LENGTH(name), name 
LIMIT 1;

SELECT name,MIN(LENGTH(name))
from user
ORDER BY LENGTH(name) ,name
limit 1
```

#### 截取字符串

```
substring_index(str,delim,count) //目标字符串str，分隔符delim，count截至第几个分隔符，right同理
substring(str, pos)  //截取从pos到末尾，pos从1开始
substring(str,pos,count) //截取从pos开始的count个字符
```

#### 获取子串

```
left(String,int count)	//截取String左边count个字符
```

#### 列出所有的数据库

```sql
SHOW DATABASES
```

#### 列出数据库的所有表

```SQL
SHOW TABLES FROM DEMO
```

#### 查询数据库表的创建语句

```SQL
SHOW CREATE TABLE TBL_NAME
```

#### 查询单个表格的字段列表

```sql
SHOW COLUMNS FROM TABLE_NAME [FROM DATABASE_NAME]
```

#### 对表格数据按条件进行归类

```sql
SELECT
CASE 
    WHEN A+B>C and B+C>A and A+C>B THEN
        CASE 
            WHEN A=B and B=C and A=C THEN 'Equilateral'
            WHEN A=B OR B=C OR A=C THEN 'Isosceles'
            ELSE 'Scalene'
        END
    ELSE 'Not A Triangle'
END       
FROM TRIANGLES
```

#### 连接字符串

```sql
CONCAT(string1,string2)
```

#### 转换大小写

```sql
lower(String)
```

#### 用户临时变量

```sql
set @var1=0;
```

> 判断某字段为NULL，用的是Some_Field  IS  NULL，不是等于号

#### 字符串转为数字

```sql
(String+0)
cast(String as signed)
```

#### 数字转换为字符串

```sql
CONVERT(23,CHAR);  
123+''
```



#### 四舍五入保留小数

```sql
round(zhi,2)	//保留两位小数
```

