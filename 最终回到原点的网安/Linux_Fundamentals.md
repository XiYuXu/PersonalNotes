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

### 从图形界面切到命令行
```
ctrl+alt+f3
```

### ubuntu开启ssh连接
1.安装包
```
sudo apt update
sudo apt install openssh-server
```
2.查看安装后是否启动了ssh服务
```
systemctl status ssh //显示active(running)成功，否则失败
```
3.若上步失败则手动开启，否则直接进4
```
/etc/init.d/ssh start
```
4.修改/etc/ssh/sshd_config登录配置文件
①将PermitRootLogin prohibit-password修改为PermitRootLogin yes，去掉前面的#（取消注释）
②去掉Port 22前的#
> 快速查找方法：在vi/vim下输入 **:/PermitRootLogin** 即可定位PermitRootLogin，其他字符串同理。利用n/N按键向上或向下查找
> 未安装vim/vi难用：先安装一下vim, apt-get install vim
5.修改配置后重启ssh服务
```
service ssh restart
```
6.允许连接通过ufw防火墙
```
ufw allow ssh
```
完事，收工~~~

### 将文件夹覆盖到另一个目录下的文件夹
本意是想将共享目录下的文件夹与linux主机上的某文件夹保持同步，首先想到mv命令，但mv的作用如下

```
/**文件操作**/
mv a.txt /tmp/b.txt     //b.txt存在则覆盖，否则相当于重命名
/**文件夹操作**/
mv aDir/ /tmp/bDir/     //若bDir存在切非空，则命令报错bDir is not Empty。若bDir为空，则会将aDir放入bDir中。若bDir不存在，则相当于重命名
```
因此在这里我们不能用mv命令。换个思路将文件夹先删掉，再用cp -r把文件夹复制过去，这样也可以保留原地址的内容不被破坏。同时cp -r能够自行创建不存在的目录
```
rm -rf /root/reactjs/app 
rm -rf /root/reactjs/public
cp -r  /mnt/hgfs/share/app /root/reactjs/app
cp -r  /mnt/hgfs/share/public /root/reactjs/public
```





