以太坊有账户的概念，有账户余额的概念。



重放攻击的防御方法是设置交易编号



账户类型：

普通账户：包含公私钥，balance，nonce

合约账户：不能主动发起交易



addr->state

160 bits 

使用merkel tree是不可行的，因为没发布一个区块就要更新整个Merkel tree， Merkel tree中的账户顺序也不一样



sorted Merkel tree新建账户代价太大

trie树（retrieval）：从头到叶子是一个编码

patricia树：压缩单子节点，但是加入新的节点，可能会导致压缩了的再返回。

![image-20200920164823746](E:%5CGithubProjs%5CMyPictures%5Cimage-20200920164823746.png)

MPT树（Merkle patricia tree）：把指针换成了hash指针的patricia tree



以太坊中利用modifyed MPT





puzzle：

随机生成一个16M cache的数组（利用seed取第一个值，然后后面的都从前一个元素通过hash运算得到），然后从cache中随机抽取一个数，通过一定算法映射到下一个要取的元素位置。填充完cache后，通过随机获得cache第一个数，通过逐次得到256个数。从这256个数中抽填充dataset的第一个元素，第2个到第datasetSize-1个元素同样如此获得。填充完dataset后，根据block header和nonce，从dataset中取得64个数，并取每个数相邻的元素，这样就获得了128个数，然后通过一定算法生成最终结果并与target比较。若不成功，调整nonce

![image-20200921190951378](E:%5CGithubProjs%5CMyPictures%5Cimage-20200921190951378.png)

权益证明和工作量证明的一异同：

权益证明是在区块链内部的，工作量证明是外部