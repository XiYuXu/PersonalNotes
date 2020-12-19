#### 对应论文地址

> https://github.com/XiYuXu/BlockChainArticles/blob/master/140.pdf

# 背景痛点

全球市场竞争加剧，为提高制造业公司竞争力，促使制造商采用更先进的技术和逻辑方法（例如云计算、网络实体系统和最近的协同式云设计系统）。然而即便这些方法在数据交互等方面有所帮助，但仍存在不能参考用户使用反馈的问题。

同时，较短的产品生命周期，对市场变化的响应能力，基于客户的设计以及快速的改进是现代制造企业的基本特征。

由此衍生出（Collaborative design and manufacturing platform）CDMP系统，能够减少设计和制造时间，从而实现更优质的产品质量，但同时也有以下不足：

<ul>
    <li>用户意见的考虑</li>
    <li>在不同部门之间分类客户的反馈困难（数据沟通问题）</li>
    <li>CDMP有些在公有云上开发，面临安全隐患以及数据传输和数据完备的滞后性</li>
</ul>

# 写作目的

回答以下问题：

- 顾客的建议如何作用到CDMP系统？
- 如何分类和聚类客户的建议以获得有用的知识？
- 如何提高CDMP系统安全性？

> this research proposed a blockchain-enabled fog computing-based collaborative design and
> manufacturing platform to develop triple communication and cooperation among the manufacturing section,
> design section, and customers in a trustable environment.

# 所用技术

- 在云环境中使用语义分析方法分析客户的建议，且利用了机器学习的方法（例如SVM）
- 使用雾计算作为系统的基础结果
- 使用区块链进行雾计算通信保障安全性

# 现实意义

the proposed platform promotes the triple connection and data
integration in the CDMP and makes customer views formulated to use
for design and manufacturing sections.

# 文章结构

**Section2：**介绍相关问题世界范围内的进展（CDMP文献综述）、客户建议处理和格式化、雾计算、区块链技术

**Section3：**提出平台

**Section4：**描述关键的技术流程

**Section5：**解释系统关键的特性和需求

**Section6：**通过说明性案例研究描述平台

**Section7、8：**讨论与总结，讲文章意义、工作的不足以及未来的展望



# 实验步骤

讲了平台分层结构，但是最后没有实现的demo



# **技术理论**

## 1.雾计算

> 如果说CDN是弥补TCP/IP本地化缓存问题，那么雾计算就是弥补**云计算本地化计算**问题!

![image-20201217210901019](https://pic.downk.cc/item/5fdc001f3ffa7d37b3111ee4.png)

> 在终端和数据中心之间再加一层，叫网络边缘层。如再加一个带有存储器的小服务器或路由器，把一些并不需要放到“云”的数据在这一层直接处理和存储，能够减小云的压力以及提升传输速率，降低时延

### **1.1雾计算VS云计算**

* 它们在网络拓扑中的位置不同，雾计算处于网络拓扑中的更低层，网络延迟更小

* 数据中心更小，雾节点更为轻量

* 雾节点拥有广泛的地域分布，一旦某一区域的服务异常，用户请求可以快速转向其他临近区域，获取相关的服务。

  

### 1.2**边缘计算 VS 云计算**(如果说云计算是集中式大数据处理，那么边缘计算可以理解为边缘式大数据处理!)

>  实际上这两者都是**处理大数据的计算运行方式**。

但不同的是，这一次，数据不用再传到遥远的云端，在边缘侧就能解决，更适合实时的数据分析和智能化处理，也更加高效而且安全。

#### 1.2.1边缘计算的特点

* 分布式和低延时计算，在智能场景有充分发挥空间。

* 对终端设备的数据进行筛选，不必每条原始数据都传送到云，充分利用设备的空闲资源，在边缘节点处过滤和分析，节能省时

* 减缓数据爆炸，网络流量的压力。

  

### 1.3边缘计算VS雾计算

雾计算 和 移动边缘计算 之间有什么区别？ - 梨享雾计算的回答 - 知乎 https://www.zhihu.com/question/54509902/answer/364144310

## 2.SVM模型

笔记见本项目：https://github.com/XiYuXu/PersonalNotes/blob/master/%E6%95%B0%E5%AD%A6%E7%90%86%E8%AE%BA/SVM%E8%AF%A6%E8%A7%A3.md



## 评价与收获

#### 1.读后感

> 文章偏于解决方案的提出，在所用技术的细节上并未做太多深入（如提到用到的SVM模型只是把SVM根本的数学来源进行照搬），优点是文章结构比较清晰，行文流畅，起承转合的过渡比较自然，或许可以作为日后写论文的指导模板。

#### 2.相关收获

> 通过网上对**区块链文献来源**的评价可以看出，或许区块链期刊更注重**研究流程的严谨性**，而对**创新型**的要求低一些。而在IEEE S&P (Oakland), ACM CCS, IACR Crypto, IACR Eurocrypto, USENIX Security，ACM PODC 等安全、密码、分布式理论的顶级会议区块链文章一般质量比较上乘。同时在**arxiv**、**eprint**等论文预收录网站，若是有一定的阅读经验，也能找到一些质量远远超过大量的顶级期刊论文。

