## 基础算子开发阶段

基础算子开发阶段需要选手们在经过培训、环境配置之后，完成两个简单而非常常用的基础算子，为后续综合算子开发打基础。这两个算子在培训阶段嘉宾们的 lecture 或多或少提到过，Triton / TileLang 技术文档中也涉及相关的例子，但我们鼓励同学们熟悉写法、自行探索。

**开发环境**：ssh 连接[类脑平台](http://114.214.255.71/heros/login/ram)(注意在校园网环境或使用 Vlab 才可以访问)。



### <strong>Assignment-1 Softmax</strong>

`Softmax` 是深度学习模型中最基础且⾼频使⽤的激活函数之⼀，⼴泛应⽤于多分类任务及 Transformer 架构（如 Attention 机制）中.在⼤模型（LLM）⻓序列推理场景下，`Softmax` 的显存读写带宽往往成为性能瓶颈。

本赛题要求选⼿在 Ascend 910B3 硬件平台上，**使⽤ Triton-Ascend 或 TileLang-Ascend 语言**（二选一即可）编写 `Softmax` 算⼦。[题面在此处](./assignment/softmax.pdf)，代码框架可以在类脑平台的共享存储获得。

- **提交窗口**：[希冀平台](cscourse.ustc.edu.cn) (cscourse.ustc.edu.cn, 初始用户名为学号，密码为学号)。进入平台之后找到“课程--算子开发创新大赛--作业1”

!!! Warning " "

    <font color=red>DDL: 2026年2月7日23:59</font>



### <strong>Assignment-2 MatMul (MM)</strong>

`MatMul`（矩阵乘法, Matrix Multiplication, MM）是深度学习模型中最核心、最基础的计算密集型算子之一，大量应用于全连接层、卷积计算的等价变换、线性映射与 Attention 计算（如 $QK^{T}$ ）中。在大模型（LLM）训练与推理场景下，`MatMul` 的性能极大地影响模型的整体吞吐率，其优化高度依赖于硬件架构特性、数据布局以及计算与访存的协同设计。

在 Ascend 等专用 AI 加速器上，`MatMul` 往往面临算力利用率不足、访存带宽受限以及数据重排开销等性能瓶颈，尤其在大规模矩阵、非对齐维度或 `batch size` 较小时更加明显。

本赛题要求选手在 Ascend 910B3 硬件平台上，**使用 Triton-Ascend 或 TileLang-Ascend 语言**（二选一即可）编写通用 `MatMul` 算子。具体要求和题面请等待正式发布。

!!! Warning " "

    <font color=red>DDL: (●′∀｀●)?</font>
