## 常用命令

#### 查看具体修改内容

```sql
git diff
```

> git status可以查看到哪些文件被修改了，但是无法显示文件具体的修改情况，这时候就可以使用git diff来查看所做的修改

#### 查看文件各个版本

```
git log
```

> 显示文件的各个版本，更简介舒服的查看方法为 

```javascript
git log --pretty=oneline
```

#### 版本回退

```sql
git reset --hard HEAD^
```

> 回退两个版本

```
git reset --hard HEAD^^
```

> 回退N个版本

```
git reset --hard HEAD~N
```

> 找到每个版本的信息

```
git reflog
```

#### 撤销修改

```
git checkout -- filename
```

> 情况一：工作区stage不为空，还有之前的文件记录，但是现在对本地文件做了修改,则该命令让本地文件回退到stage版本
>
> 情况二：工作区未提交，只做了本地修改，则回退到版本库状态
>
> 情况三：版本库，工作区，本地都不同，则还原到stage状态

#### 创建并切换分支

```
git checkout -b dev
```

#### 查看当前分支

```
git branch
```

#### 切换分支

```
git checkout master
```

#### 合并分支（就像插入）

```
git merge dev
```

删除分支

```
git branch -d dev
```

#### 生成提交信息的合并

```git
git merge --no--ff -m "no fast-forward" dev
```

> 合并分支过程中，默认是使用fast-forward模式的。若是合并之后删除dev分支，则会丢失掉分支信息，而禁用之后，Git会把合并看成是一个新的commit，所以日常开发中多用--no--ff参数保存信息。

#### 复刻已完成的一次提交操作

```
git cherry-pick 4c805e2
```

#### 保存当前工作环境

```
git stash
```

#### 获取远程库并在dev分支上开发

```
 git checkout -b dev origin/dev
```