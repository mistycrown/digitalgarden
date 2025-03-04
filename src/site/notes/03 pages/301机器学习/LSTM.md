---
{"dg-publish":true,"permalink":"/03 pages/301机器学习/LSTM/","created":"2025-02-26T13:54:11.172+08:00","updated":"2025-03-04T14:19:17.181+08:00"}
---

## 公式详解
**遗忘门 (Forget Gate)**
$$
f_{t}=\sigma(W_{f}[h_{t-1},x_{t}]+b_{f})
$$
- **Wf**：权重矩阵（Weight Matrix），决定历史信息 ht−1 和当前输入 xt 对遗忘门的影响。
- **bf**：偏置项（Bias），给计算结果增加一个基础量。
- 拼接向量
	- **ht−1**：上一时刻的隐藏状态（Hidden State），保存了之前步骤的记忆。
	- **xt**：当前时刻的输入（比如当前的字或语素）。
- **σ**：Sigmoid 激活函数，将结果压缩到0~1之间。
    - _作用_：0表示“完全遗忘”，1表示“完全保留”。

**输入门（Input Gate）**
$$
i_{t}=\sigma(W_{i}\left[h_{t-1},x_{t}\right]+b_{i})
$$
$$
\widehat{\mathrm{cell}_{t}}=\operatorname{tanh}(W_{c}[h_{\mathrm{t-1}},x_{\mathrm{t}}]+b_{\mathrm{c}})
$$
- **Wi,Wc**：输入门的权重矩阵，分别控制“是否更新”和“候选记忆内容”。
- **bi,bc**：对应的偏置项。
- **tanh⁡**：双曲正切函数，将结果压缩到-1~1之间。

 **细胞状态更新（Cell State）**
$$
\mathrm{cell}_{t}=f_{t}\odot\mathrm{cell}_{t-1}+i_{t}\odot\widehat{\mathrm{cell}_{t}}
$$
- **⊙**：逐元素相乘（Hadamard Product）。
- **cellt−1**：上一时刻的细胞状态（长期记忆）。
- **cellt^**：当前候选记忆（短期记忆）

**输出门（Output Gate）**
$$
\smash{o_{t}=\sigma(W_{o}\left[h_{t-1},x_{t}\right]+b_{o})}

\mathrm{hidden}_{t}=o_{t}\odot\operatorname{tanh}(\mathrm{cell}_{t})
$$
- **Wo**：输出门的权重矩阵，控制输出哪些信息。
- **ot**：输出门的开关，决定当前细胞状态有多少传递到隐藏状态。
