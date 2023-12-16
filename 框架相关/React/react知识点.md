## React Hooks指南
###Q:为什么需要React Hooks
**为了迎合函数式编程，摆脱class类型组件的使用，转而使用Function完成所有组件的代码。**
###Q:为什么要拒绝使用class设计
####class的不利之处
①难以复用组件间状态逻辑：
②难以维护复杂组件：
③this指向问题

####使用Hook的好处
Hook 的优势
Hook 使你在无需改变组件结构的情况下复用状态逻辑（自定义 Hook）
Hook 将组件中互相关联的部分拆分成更小的函数（比如设置订阅或请求数据）
Hook 使你在非 class 的情况下可以使用更多的 React 特性


## 踩坑
> 当试图利用useEffect向window对象绑定一个kewdown事件，可能是因为绑定的事件处理函数在单次绑定时会将state永久化，不读取新的state，就会造成在处理函数中已经更新state但是未来拿的还是初始值的情况，对此需要多次调用useEffect反复绑定函数（反复更新state值），这样才能够将最新的state作用到其中去。所以如果出现每次更新都会覆盖掉之前更新的情况，多半是useEffect只调用了一次，固化的state只能记住最近的一步操作。
![](https://raw.githubusercontent.com/XiYuXu/MyPictures/master/Snipaste_2023-12-04_20-01-45.jpg)
