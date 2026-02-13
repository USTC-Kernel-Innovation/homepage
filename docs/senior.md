## 综合算子开发阶段

综合算子开发阶段需要选手们完成两个较为复杂的实用算子，它们的思想和实现均来源于前沿论文。

这两个算子在培训阶段[lecture 9](./course.md#lecture-9-transformer--llm-infer) 被提到，培训页面包含了一些论文及网页资料供大家参考。实现进阶算子时，我们不限制大家对大模型辅助生成代码的使用。

**开发环境**：ssh 连接[类脑平台](http://114.214.255.71/heros/login/ram)


### <strong>Assignment-3 Paged Attention</strong>

分页注意力（Paged Attention）是一种高效实现注意力键值缓存（KV cache）的方法，它采用固定大小的“页”（块）结构，因此无需为每个序列分配一个大型连续缓冲区。每个序列的 KV cache 存储在页列表中，attention 通过 index map 从这些页中读取数据。这种设计减少了碎片化问题，并能高效批处理大量可变长度序列。

本赛题要求选手在 Ascend 910B3 硬件平台上，**使用 Triton-Ascend 或 TileLang-Ascend 语言**（二选一即可）编写通用 `MatMul` 算子。[题面在此处](./assignment/paged.pdf)，代码框架可以在类脑平台的共享存储获得。

- **提交窗口(稍后创建)**：[希冀平台](cscourse.ustc.edu.cn) (cscourse.ustc.edu.cn, 初始用户名为学号，密码为学号)。进入平台之后找到“课程--算子开发创新大赛--作业3”。 提交窗口创建好之后会在 QQ 群通知，在此之前，同学们可以复习 Paged Attention 的原理，努力实现更高的加速比 ovo）

- **请不要随意删除 print 的内容，评测机修复好之后，会有相关的评分标准！**

!!! Warning "注意"

    DDL：2026年3月3日 (●′∀｀●)


### <strong>Assignment-4 Sparse Attention</strong>