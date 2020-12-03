### 注入配置

![image-20200705120125558](C:\Users\XiaoChuanye\AppData\Roaming\Typora\typora-user-images\image-20200705120125558.png)



#### 一般属性注入

```xml
<bean id=""  class="" >

	<property name="" value=""/>

</bean>
```

#### 引用注入

```xml
<bean id="" class="">

	<property name="" ref="" />

</bean>
```

#### 数组注入

```xml
    <property name="names">
        <list>
            <value>张三</value>
            <value>李四</value>
            <value>王五</value>
        </list>
    </property>

```
#### map注入

```xml
<property name="map">
    <map>
        <entry key="username" value="张三"/>
        <entry key="password" value="123456"/>
    </map>
</property>
    
```

#### props注入

```xml
<property name="properties">
    <props>
        <prop key="username">赵六</prop>
    </props>
</property>
```





### AOP配置

#### 插入对象指定插入位置:

![image-20200706093251139](C:\Users\XiaoChuanye\AppData\Roaming\Typora\typora-user-images\image-20200706093251139.png)

#### 被插入对象为主体描述方法执行顺序

![image-20200706094026091](C:\Users\XiaoChuanye\AppData\Roaming\Typora\typora-user-images\image-20200706094026091.png)

