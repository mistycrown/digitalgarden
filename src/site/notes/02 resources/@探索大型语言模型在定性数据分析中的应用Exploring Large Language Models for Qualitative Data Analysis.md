---
{"dg-publish":true,"permalink":"/02 resources/@探索大型语言模型在定性数据分析中的应用Exploring Large Language Models for Qualitative Data Analysis/","created":"2025-03-21T12:39:23.828+08:00","updated":"2025-03-30T14:13:30.642+08:00"}
---


## 摘要

本文研究了如何利用大型语言模型（LLMs）提升汉堡大学开发的开源定性数据分析（QDA, qualitative data analysis）平台——**话语分析工具套件（DATS,The Discourse Analysis Tool Suite）** 的工作效率。作者识别出QDA工作流程中的多个AI辅助机会，并将其转化为四项自然语言处理（NLP）任务：

- **文档分类**：对文档进行类别划分。  
- **信息提取**：从文本中提取关键信息。  
- **跨度分类**：对文本片段进行标注。  
- **文本生成**：生成摘要或优化文本。  

研究通过英语和德语数据集构建了一个QDA专用基准，评估了三款开源LLMs的表现：**Llama 3.1**、**Gemma 2** 和 **Mistral NeMo**。结果显示，LLMs在英语任务中表现优异，因此在DATS中集成了一个可选的**LLM助手**功能。本研究旨在通过开源方式推动QDA的AI能力普及。

---

## 主要内容

### 1. 引言

DATS是一个为数字人文（DH）学者设计的开源QDA平台，基于**扎根理论研究**，支持大规模、非结构化数据的管理与分析。其核心工作流程包括：

- 通过元数据和标签组织文档。  
- 对文本段落进行层次化编码。  
- 记录研究见解。  

这些任务中，元数据提取和文档分类耗时，编码和摘要则需要较高专业性。作者通过LLMs简化这些流程，评估其在四项NLP任务中的表现，并将**LLM助手**集成到DATS中，重点服务英语项目。

**研究贡献：**  
- 提出了AI辅助QDA工作流程。  
- 设计了QDA任务基准。  
- 测试了开源LLMs的表现。  
- 提供了DATS中LLM集成的实现细节。

> [!TIP] Grounded Theory-based research💡
>  [Grounded theory - Wikipedia](https://en.wikipedia.org/wiki/Grounded_theory)
>  [[00 inbox/扎根理论研究\|扎根理论研究]]（Grounded Theory-based research）是一种定性研究方法，由巴尼·格拉泽（Barney Glaser）和安塞尔姆·斯特劳斯（Anselm Strauss）在20世纪60年代提出，旨在通过系统收集和分析数据，从中发展出理论，而不是从预设假设开始验证。它特别适用于探索社会过程和复杂现象，强调理论必须“扎根”于数据本身。
>  - **数据收集与分析并行**：研究者边收集数据边分析，逐步发现模式。
>  - **常比较法**：通过不断比较数据，识别类别和关系，确保理论与数据紧密相关。
>  - **编码过程**：包括开放编码（分解数据，命名概念）、轴心编码（连接类别，构建关系）和选择性编码（围绕核心类别整合理论）。
>  - **理论抽样**：根据已发现的概念选择新数据，以细化理论。
>  - **备忘录**：记录分析过程中的见解，帮助理论构建。

### 2. 相关工作

#### QDA平台与AI
现有QDA平台如**MAXQDA**、**NVivo**和**Atlas.ti**已开始整合AI功能（如摘要、情感分析），但多为付费且依赖第三方数据处理，存在隐私风险。相比之下，DATS开源、免费，支持本地运行。

#### LLM研究
现有LLM基准（如MMLU、SuperGLUE）与QDA实际需求关联不大。本文受**Ziems et al. (2024)** 启发，探索LLMs在零样本任务中的潜力，并特别关注英语和德语数据。

---

### 3. AI辅助工作流程示例

**场景：** 研究者Alice分析CEO访谈，研究公司社会影响。  
**流程：**  
1. 在DATS中创建项目，定义标签和元数据。  
2. 上传录音，使用**Whisper**转录。  
3. AI建议标签和元数据，用户验证。  
4. 构建编码系统，AI自动标注文本。  
5. AI优化文本流畅性并生成摘要。  

AI显著提升了效率，帮助Alice快速完成分析。

---

### 4. QDA任务基准

#### 评估模型
测试了三款开源LLMs：  
- **Llama 3.1 (8B)**：多语言，128k上下文。  
- **Gemma 2 (9B)**：轻量，英语为主。  
- **Mistral NeMo (12B)**：多语言，支持代码。  

#### 任务与结果
1. **文档分类**  
   - 数据集：Tagesschau（德语）、BBC（英语）、IMDb（多标签）。  
   - 结果：Gemma 2表现最佳（F1约64），德语细粒度任务较弱。

2. **信息提取**  
   - 数据集：SQuAD（英语）、GermanQuAD（德语）、MUC-4（模板填充）。  
   - 结果：Gemma 2在问答中领先（F1约79），Llama 3.1在模板填充中较优。

3. **跨度分类**  
   - 数据集：Few-NERD（英语）、German LER（德语）、引文归属（德语）。  
   - 结果：Gemma 2最佳（F1约30-38），德语任务难度较高。

4. **文本生成**  
   - 数据集：Disf-QA（英语）、DISCO（英德）、CNN/DM（英语）、MLSUM（德语）。  
   - 结果：Gemma 2在纠正流畅性中最佳（R-1约84），德语生成表现较差。

> [!TIP] Span Classification💡
>  **跨度分类**（Span Classification）是自然语言处理（NLP）中的一种任务，旨在识别文本中的特定**文本片段**（称为“跨度”），并为这些片段分配预定义的类别或标签。这些跨度可以是一个词、一个短语，或者一个完整的句子。跨度分类的一个典型应用是**命名实体识别（NER）**
>  ### 在定性数据分析（QDA）中的应用
>  跨度分类在**定性数据分析（QDA）** 项目中非常重要，尤其是在遵循**扎根理论**范式的中文研究中。扎根理论是一种通过系统性编码来构建理论的方法，而跨度分类可以帮助自动化这一过程。
>  扎根理论的编码阶段
>  1. **开放编码**（Open Coding）：将中文文本分解为初步的概念或类别。例如，将“李白是个伟大的诗人”标注为“人物”和“评价”。
>  2. **选择性编码**（Selective Coding）：聚焦于核心类别，进一步细化。例如，专注于“诗人”这一类别。
>  3. **轴心编码**（Axial Coding）：将类别连接起来，形成一个完整的框架，例如“诗人”与“唐朝文化”之间的关系。
> 

#### 讨论
- **Gemma 2**整体表现最优
- 德语任务普遍表现不如英语。

### 5. LLM集成

**LLM助手**在DATS中实现为可选功能，支持标签建议、元数据提取和文本标注。  
**操作流程：**  
1. 选择任务。  
2. 指定目标。  
3. 审查AI提示。  
4. 后台执行任务。  
5. 验证结果。  

**技术实现：**  
- 前端：React。  
- 后端：Ollama（运行Gemma 2）、FastAPI、Celery。  

### 6. 结论与未来工作

LLMs（尤其是Gemma 2）有效增强了DATS的QDA能力，目前已支持英语项目。未来计划包括：  
- 自动建议新标签和代码。  
- 使用领域特定数据。  
- 探索少样本学习和微调。

---

### 7. 局限性

- **零样本限制**：难以捕捉项目特定细节。  
- **语言限制**：德语表现不如英语。  
- **数据集匹配性**：基准任务与实际QDA需求有差距。  
- **LLM局限**：推理和偏见问题需用户验证。
