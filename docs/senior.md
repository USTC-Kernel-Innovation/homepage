## 进阶算子开发阶段

进阶算子开发阶段需要选手们完成两个较为复杂的实用算子，它们的思想和实现均来源于前沿论文。

这两个算子在培训阶段[lecture 9](./course.md#lecture-9-transformer--llm-infer) 被提到，培训页面包含了一些论文及网页资料供大家参考。实现进阶算子时，我们不限制大家对大模型辅助生成代码的使用。

**开发环境**：ssh 连接[类脑平台](http://114.214.255.71/heros/login/ram)


### <strong>Assignment-3 Paged Attention</strong>

分页注意力（Paged Attention）是一种高效实现注意力键值缓存（KV cache）的方法，它采用固定大小的“页”（块）结构，因此无需为每个序列分配一个大型连续缓冲区。每个序列的 KV cache 存储在页列表中，attention 通过 index map 从这些页中读取数据。这种设计减少了碎片化问题，并能高效批处理大量可变长度序列。

!!! Warning "注意"

    DDL：？ (●′∀｀●)