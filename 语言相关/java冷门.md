>  局部变量在声明时应该初始化，java语言机制不提供默认值

> 使用默认访问修饰符声明的变量和方法，对同一个包内的类是可见的。接口里的变量都隐式声明为 public static final,而接口里的方法默认情况下访问权限为 public。

#### 生成指定格式的时间

```java
public class Main {
    public static void main(String[] args) {
        // 自定义格式化:
        DateTimeFormatter dtf = DateTimeFormatter.ofPattern("yyyy/MM/dd HH:mm:ss");
        System.out.println(dtf.format(LocalDateTime.now()));

        // 用自定义格式解析:
        LocalDateTime dt2 = LocalDateTime.parse("2019/11/30 15:16:17", dtf);
        System.out.println(dt2);
    }

}
```

#### 时间处理类

```c

java.time.LocalDate  ->只对年月日做出处理

java.time.LocalTime  ->只对时分秒纳秒做出处理

java.time.LocalDateTime ->同时可以处理年月日和时分秒
```

#### Map操作

##### 包含值

```java
if(map.containsKey(key))
```

##### 根据key返回value

```java
map.get(key)
```

