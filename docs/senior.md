## 综合算子开发阶段

综合算子开发阶段需要选手们完成两个较为复杂的实用算子，它们的思想和实现均来源于前沿论文。

这两个算子在培训阶段[lecture 9](./course.md#lecture-9-transformer--llm-infer) 被提到，培训页面包含了一些论文及网页资料供大家参考。实现进阶算子时，我们不限制大家对大模型辅助生成代码的使用。

**开发环境**：ssh 连接[类脑平台](http://114.214.255.71/heros/login/ram)


### <strong>Assignment-3 Paged Attention</strong>

分页注意力（Paged Attention）是一种高效实现注意力键值缓存（KV cache）的方法，它采用固定大小的“页”（块）结构，因此无需为每个序列分配一个大型连续缓冲区。每个序列的 KV cache 存储在页列表中，attention 通过 index map 从这些页中读取数据。这种设计减少了碎片化问题，并能高效批处理大量可变长度序列。

本赛题要求选手在 Ascend 910B3 硬件平台上，**使用 Triton-Ascend 或 TileLang-Ascend 语言**（二选一即可）编写通用 `MatMul` 算子。[题面在此处](./assignment/Paged_attn_scripts.pdf)，代码框架可以在类脑平台的共享存储获得。

- **提交窗口**：[希冀平台](cscourse.ustc.edu.cn) (cscourse.ustc.edu.cn, 初始用户名为学号，密码为学号)。进入平台之后找到“课程--算子开发创新大赛--进阶算子 Paged attention”。 

- **请不要随意删除 print 的内容，详见↑题面↑！**

- <font color=red>助教们在培训页面放了一些关于 Paged Attention 的论文、专栏、讲解，大家有时间一定要看看~</font>

!!! Warning "注意"

    DDL：2026年3月3日 (●′∀｀●)


### <strong>Assignment-4 Sparse Attention</strong>

Sparse attention 是为了解决标准自注意力在长序列下计算量随长度平方增长的问题而提出的改进方法。在原始 Transformer 中，每个 token 都需要和所有其他 token 计算注意力，因此时间和显存开销都很高。Sparse attention 的基本思想是只计算“部分”注意力，例如限制在局部窗口或特定块结构中，从而把复杂度从 $O(n^2)$ 降到接近线性规模。这种方法在长文本建模和大模型推理中可以显著降低资源消耗，但由于稀疏模式通常是预先设定的，因此可能削弱对远距离依赖的建模能力。

带 quest 的 sparse attention 在此基础上进一步引入“查询感知”的动态选择机制。它不再固定哪些 token 可以互相关注，而是根据当前 Query 的内容，通过粗粒度相似度估计、Top-k 选择或近似最近邻检索等方式，先筛选出最相关的一小部分 Key，再对它们进行精确计算。这样既避免了全量计算，又保留了跨长距离建模的能力。整体来看，quest 机制使注意力从固定结构的稀疏计算，转变为“先检索、再计算”的两阶段过程，更适合超长上下文和大规模推理场景。

本赛题要求选⼿在 Ascend 910B3 硬件平台上，**使⽤ Triton-Ascend 或 TileLang-Ascend 语言**（二选一即可）编写 `xxxxx` ，代码框架可以在类脑平台的共享存储获得。


!!! Warning "注意"

    <font color=red>还没有内容~</font>

