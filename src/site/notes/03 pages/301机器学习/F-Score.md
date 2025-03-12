---
{"dg-publish":true,"permalink":"/03 pages/301机器学习/F-Score/","created":"2024-11-30T20:42:20.487+08:00","updated":"2025-03-12T19:42:45.700+08:00"}
---

F 值（F-Mea-sure 或 F-Score）评价指标，其是精确率（Precision）和召回率（Recall）的加权调和平均
![Pasted image 20230521213758.png](/img/user/09%20settings/Z%20attachment/Pasted%20image%2020230521213758.png)
β是加权调和参数；P 是精确率；R 是召回率。当β=1 时，即精确率和召回率的权重相同，此时 F 值又称为 F 1 值，具体公式为：![Pasted image 20230521213819.png](/img/user/09%20settings/Z%20attachment/Pasted%20image%2020230521213819.png)
在命名实体识别问题中，精确率和召回率的定义分别为
![Pasted image 20230521213840.png](/img/user/09%20settings/Z%20attachment/Pasted%20image%2020230521213840.png)

