> E:\Live And Learn\论文写作\Article\BlockChainSCI\140

## 背景痛点

全球市场竞争加剧，为提高制造业公司竞争力，促使制造商采用更先进的技术和逻辑方法（例如云计算、网络实体系统和最近的协同式云设计系统）。然而即便这些方法在数据交互等方面有所帮助，但仍存在不能参考用户使用反馈的问题。

同时，较短的产品生命周期，对市场变化的响应能力，基于客户的设计以及快速的改进是现代制造企业的基本特征。

由此衍生出（Collaborative design and manufacturing platform）CDMP系统，能够减少设计和制造时间，从而实现更优质的产品质量，但同时也有以下不足：

<ul>
    <li>用户意见的考虑</li>
    <li>在不同部门之间分类客户的反馈困难（数据沟通问题）</li>
    <li>CDMP有些在公有云上开发，面临安全隐患以及数据传输和数据完备的滞后性</li>
</ul>

## 写作目的

回答以下问题：

- 顾客的建议如何作用到CDMP系统？
- 如何分类和聚类客户的建议以获得有用的知识？
- 如何提高CDMP系统安全性？

> this research proposed a blockchain-enabled fog computing-based collaborative design and
> manufacturing platform to develop triple communication and cooperation among the manufacturing section,
> design section, and customers in a trustable environment.

## 所用技术

- 在云环境中使用语义分析方法分析客户的建议，且利用了机器学习的方法（例如SVM）
- 使用雾计算作为系统的基础结果
- 使用区块链进行雾计算通信保障安全性

## 现实意义

the proposed platform promotes the triple connection and data
integration in the CDMP and makes customer views formulated to use
for design and manufacturing sections.

## 文章结构

**Section2：**介绍相关问题世界范围内的进展（CDMP文献综述）、客户建议处理和格式化、雾计算、区块链技术

**Section3：**提出平台

**Section4：**描述关键的技术流程

**Section5：**解释系统关键的特性和需求

**Section6：**通过说明性案例研究描述平台

**Section7、8：**讨论与总结，讲文章意义、工作的不足以及未来的展望



## 实验步骤

讲了平台分层结构，但是最后没有实现的demo



## **技术理论**

#### 1.雾计算概念（**如果说CDN是弥补TCP/IP本地化缓存问题，那么雾计算就是弥补云计算本地化计算问题！**）

![image-20201217210901019](https://pic.downk.cc/item/5fdc001f3ffa7d37b3111ee4.png)

> 在终端和数据中心之间再加一层，叫网络边缘层。如再加一个带有存储器的小服务器或路由器，把一些并不需要放到“云”的数据在这一层直接处理和存储，能够减小云的压力以及提升传输速率，降低时延

#### **2.雾计算对比云计算**

