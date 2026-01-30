## 基础算子开发阶段

基础算子开发阶段需要选手们在经过培训、环境配置之后，完成两个简单而非常常用的基础算子，为后续综合算子开发打基础。这两个算子在培训阶段嘉宾们的 lecture 或多或少提到过，Triton / TileLang 技术文档中也涉及相关的例子，但我们鼓励同学们熟悉写法、自行探索。

**开发环境**：ssh 连接[类脑平台](http://114.214.255.71/heros/login/ram)(连接方法见[lecture-4](./course.md#lecture-4-environment-setup), 注意必须在校园网环境或使用 Vlab 才可以访问)。

**提交窗口**：[希冀平台](cscourse.ustc.edu.cn) (cscourse.ustc.edu.cn, 初始用户名为学号，密码为学号)。

### Assignment-1 Softmax

`Softmax` 是深度学习模型中最基础且⾼频使⽤的激活函数之⼀，⼴泛应⽤于多分类任务及 Transformer 架构（如 Attention 机制）中.在⼤模型（LLM）⻓序列推理场景下，`Softmax` 的显存读写带宽往往成为性能瓶颈。

本赛题要求选⼿在 Ascend 910B3 硬件平台上，**使⽤ Triton-Ascend 或 TileLang-Ascend 语言**（二选一即可）编写 `Softmax` 算⼦。具体要求和题面请等待正式发布。
!!! Warning " "

    <font color=red>DDL: (●′∀｀●)?</font>

### Assignment-2 MatMul (MM)


!!! Info " "

    (●′∀｀●) 现在还什么都没有 (●′∀｀●)