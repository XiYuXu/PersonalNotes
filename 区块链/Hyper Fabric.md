##  key design features

### 1.assets

一切有价值之物

### 2.ChainCode



### 3.Ledger Features

> 不可更改共享的账本,为每个channel保存了这个交易历史记录，并提供了类sql语言对整个交易历史进行查询，方便高效地审计或者解除纠纷。

#### 账本查询特性：

- 查询使用key查找，范围查找和复合key查找
- 只读查找使用富查找语言
- 历史记录查找——通过某历史记录地key查找数据地出处
- 交易由state之前地键值对状态和之后写在合约里的状态组成
- 交易包含了用户的签名并交付给ordering service

### 4.Privacy

### 5.Security & Membership Services 

> 确保区块链是安全的，所有入链地节点都不可避免地要收到相关的监控

### 6.Consensus

> 独一无二的共识机制使得区块链共识更有伸缩性和灵活性



