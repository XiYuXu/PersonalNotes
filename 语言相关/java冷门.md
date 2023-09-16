>  局部变量在声明时应该初始化，java语言机制不提供默认值

> 使用默认访问修饰符声明的变量和方法，对同一个包内的类是可见的。接口里的变量都隐式声明为 public static final,而接口里的方法默认情况下访问权限为 public

> 抽象方法能不能是静态的，不能的，因为抽象方法注定是要被重写的，而静态方法是不能重写的，所以抽象方法不能是静态方法
> 内部类与静态内部类的区别：1.**静态内部类**相对与**外部类**是独立存在的，在静态内部类中**无法直接访问**外部类中变量、方法。如果 要访问的话，必须要new一个外部类的对象，使用new出来的对象来访问。但是可以直接访问静态的变量、调用静态的方法;而普通内部类作为外部类一个成员而存在，在普通内部类中可以直接访问外部类属性，调用外部类的方法。2.静态内部类的实例化不依赖于外部类的实例，可以直接通过类名访问；而非静态内部类的实例化必须依赖于外部类的实例，只能在外部类的实例方法中创建。
>
> comparator和comparable的区别：前者是一个能够生产比较器的接口，程序员能够通过定义多个比较器完成不侵入原始bean代码的多样化比较，而后者着重强调类自身的功能，通过实现一个compareTo方法完成较为单一的比较。

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

#### 根据下标范围截取子串
```
String greeting = "hello";
String subString = greeting.subString(0,3); //截取到下标范围0~2的"hel"，子串长度为3-0
```

#### 寻找子串
> 返回与字符串str或代码点cp匹配的第一个子串的开始位置。这个位置从索引0或fromIndex开始计算。如果在原始串中不存在str，返回-1。
1.int index0f(String str)
2.int index0f(String str, int fromIndex)
3.int index0f(int cp)
4.int index0f(int cp, int fromIndex)

#### Scanner与控制台
```
Scanner in = new Scanner(System.in);
String name = in.nextLine(); //输入英文名时可以打空格
String word = in.next();     //只想输入一个单词，可以用空格作为分隔符
```
#### 用String.format()创建一个格式化的字符串
```
String greeting = String.format("hello %s",userName);
```
#### 创建数组
![](https://raw.githubusercontent.com/XiYuXu/MyPictures/master/20230912225625.png)



#### 复制数组的区别
1.引用相同的内存空间
```
int []raw = new int[10];
int []result = raw;    //result和raw可以相互替换
```
2.完全指向不同空间的复制
```
/*将raw数组的内容复制到result中，result长度为raw.length*/
int []reuslt = Arrays.copyOf(raw,raw.length);
/*将raw数组空间翻倍*/
raw = Arrays.copyOf(raw,raw.length*2);
/*复制某一数组范围，下标从start至end-1*/
int []result = Arrays.copyOfRange(raw,start,end);
```

#### 填充数组
```
Arrays.fill(type[] raw,type value); //用value填充相同type的数组raw
```

#### 时间相关的LocalDate
1.初始化一个变量
```
LocalDate a = LocalDate.now(); //静态工厂方法， 不用new对象
LocalDate a = LocalDate.of(1992,12,28); //静态工厂方法， 不用new对象
```
2.获取年月日星期几
```
int year = a.getYear();
int month = a.getMonthValue();
int day = a.getDayOfMonth();
int day = a.getDayOfWeek();
```
3.日期向前后推
```
LocalDate time = a.plusDays(days);
LocalDate time = a.minusDays(days);
```

#### 访问修饰符
- **private** 仅对本类可见
- **public** 对所有类可见
- **protected** 对本包和子类可见
- **无修饰符** 对本包可见


#### 不用循环打印数组
1.打印一维数组
```
直接用Arrays的静态Arrays.toString([]nums);
```
2.打印多维数组
```
Arrays.deepToString([][]nums);
```


### 反射
#### 获取类名
```
e.getClass().getName();  //如果类在包内，包名也打印
```
#### 根据类名获取类
```
Class.forName(className);   //根据类路径className得到类
```
#### 动态地创建一个类的实例
```
e.getClass().newInstance();  //如果类在包内，包名也打印
```

### 集合
![](https://raw.githubusercontent.com/XiYuXu/MyPictures/master/20230916002048.png)