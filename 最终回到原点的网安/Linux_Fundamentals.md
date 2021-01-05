最近在youtube上被种草一个有意思的网站，https://overthewire.org/wargames/

是以**CTF**(capture the flag)的方式让你重温或者熟悉基础的linux指令。同时也是**网络安全入门**的一个非常棒的资源

话不多说，以下是对于第一个挑战bandit的总结（把内容提纯）：

### 使用ssh以特定账号密码登陆ssh服务器

> `ssh username@ipaddr`//指定用户以及IP地址登陆
>
> ssh -p portnum username@ipaddr //指定端口、用户、以及ip地址登陆

### 查看当前目录下文档的类型

![image-20210105204613945](E:\GithubProjs\MyPictures\image-20210105204613945.png)



### find默认操作的上下文是当前目录及其子目录

> 有很多参数、-iname、-type 、-size  、-perm

> find命令很多可以查看https://zhuanlan.zhihu.com/p/49925542



