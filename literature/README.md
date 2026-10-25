# 文献阅读记录

这里保存与“基于多模态大模型的视频动作序列检测”相关的阅读笔记。

## 一、主线必读

| 编号 | 论文 | 主题 | 阅读状态 | 笔记 | 阅读启发 |
| --- | --- | --- | --- | --- | --- |
| 01 | [TimeChat](https://openaccess.thecvf.com/content/CVPR2024/html/Ren_TimeChat_A_Time-sensitive_Multimodal_Large_Language_Model_for_Long_Video_CVPR_2024_paper.html) | 长视频时间理解、多模态大模型 | 第一遍已读完 | [笔记](timechat.md) | 也许我们可以基于现有模型，构造我们自己的数据集，仿照他的思路，免去第一阶段较大的训练量，将主要精力放在第二阶段LoRA的参数调节上（重点：TimeIT 并不只训练一种视频任务，而是将多种需要建立“视频语义 - 时间戳”对应关系的任务统一为语言指令数据。**密集视频描述**：连续找出多个动作或事件；**步骤定位与描述**：给动作步骤标出起止时间；**时间视频定位**：根据一个动作描述，找出它发生的片段。这样面对不同提问就能更全面的回答“某段时间在干什么”），让模型学会识别我们的主要动作流（？？单一动作流还是多样化工作流还未知）|
| 02 | [VTimeLLM](https://openaccess.thecvf.com/content/CVPR2024/html/Huang_VTimeLLM_Empower_LLM_to_Grasp_Video_Moments_CVPR_2024_paper.html) | 视频时间定位、细粒度事件理解 | 待读（下一篇） | 待创建：`vtime_llm.md` |和timechat加上时间戳来表示时序不同，该模型不额外设置视觉时序模块，主要依赖顺序视觉 token 与 LLM。这个模型于视频动作检测相关程度很高，我觉得他这里的重点就在于他提出“特征对齐  -> 边界感知  -> 指令微调”三阶段的训练流程，去提高细粒度视频时刻理解能力，相当于使模型能够按顺序识别出每个动作。按顺序生成“动作类别 + 起止位置”。|
| 03 | [TRACE: Temporal Grounding Video LLM via Causal Event Modeling](https://proceedings.iclr.cc/paper_files/paper/2025/hash/df027cf11469e746ef94d583f9f5537f-Abstract-Conference.html) | 事件建模、时间定位、结构化事件序列 | 待读 | 待创建：`trace.md` | |
| 04 | [TemporalVLM](https://aclanthology.org/2026.findings-acl.70/) | 长视频时序推理、时序动作分割 | 待读 | 待创建：`temporal_vlm.md` | |
| 05 | [What Happens When: Learning Temporal Orders of Events in Videos（MECoT）](https://doi.org/10.1109/WACV61042.2026.00273) | 多事件时序推理、动作先后顺序 | 待读 | 待创建：`mecot.md` | |
| 06 | [Foresee-to-Ground: From Predictive Temporal Perception to Evidence-Driven Reasoning for Video Temporal Grounding](https://proceedings.mlr.press/v306/zheng26l.html) | 候选片段预测、证据驱动的精细时间定位 | 待读 | 待创建：`foresee_to_ground.md` | |

## 二、其余 10 篇：按专题补充阅读

### A. 视频时间定位的早期代表方法

| 编号 | 论文 | 主题 | 阅读状态 | 笔记 | 阅读启发 |
| --- | --- | --- | --- | --- | --- |
| 07 | [HawkEye: Training Video-Text LLMs for Grounding Text in Videos](https://arxiv.org/abs/2403.10228) | 视频文本对齐、文本条件时间定位 | 待读 | 待创建：`hawkeye.md` | |
| 08 | [Momentor: Advancing Video Large Language Model with Fine-Grained Temporal Reasoning](https://proceedings.mlr.press/v235/qian24a.html) | 细粒度时间推理、片段级视频理解 | 待读 | 待创建：`momentor.md` | |

### B. 时间戳表示与时序特征建模

| 编号 | 论文 | 主题 | 阅读状态 | 笔记 | 阅读启发 |
| --- | --- | --- | --- | --- | --- |
| 09 | [VTG-LLM: Integrating Timestamp Knowledge into Video LLMs for Enhanced Video Temporal Grounding](https://ojs.aaai.org/index.php/AAAI/article/view/32341) | 时间戳表示、视觉 Token 压缩 | 待读 | 待创建：`vtg_llm.md` | |
| 10 | [Grounded-VideoLLM: Sharpening Fine-grained Temporal Grounding in Video Large Language Models](https://aclanthology.org/2025.findings-emnlp.50/) | 双流时序建模、细粒度时间定位 | 待读 | 待创建：`grounded_videollm.md` | |
| 11 | [Seq2Time: Sequential Knowledge Transfer for Video LLM Temporal Grounding](https://openaccess.thecvf.com/content/CVPR2025/html/Deng_Seq2Time_Sequential_Knowledge_Transfer_for_Video_LLM_Temporal_Grounding_CVPR_2025_paper.html) | 时序知识迁移、序列训练数据 | 待读 | 待创建：`seq2time.md` | |

### C. 更精确的动作边界预测

| 编号 | 论文 | 主题 | 阅读状态 | 笔记 | 阅读启发 |
| --- | --- | --- | --- | --- | --- |
| 12 | [TimeRefine: Temporal Grounding with Time Refining Video LLM](https://arxiv.org/abs/2412.09601) | 时间边界迭代修正、精细定位 | 待读 | 待创建：`time_refine.md` | |
| 13 | [DisTime: Distribution-based Time Representation for Video Large Language Models](https://openaccess.thecvf.com/content/ICCV2025/html/Zeng_DisTime_Distribution-based_Time_Representation_for_Video_Large_Language_Models_ICCV_2025_paper.html) | 时间分布表示、连续时间预测 | 待读 | 待创建：`distime.md` | |
| 14 | [TimeExpert: An Expert-Guided Video LLM for Video Temporal Grounding](https://openaccess.thecvf.com/content/ICCV2025/html/Yang_TimeExpert_An_Expert-Guided_Video_LLM_for_Video_Temporal_Grounding_CVPR_2025_paper.html) | 混合专家模型、任务专门化 | 待读 | 待创建：`time_expert.md` | |

### D. 高阶推理、智能体与训练策略

| 编号 | 论文 | 主题 | 阅读状态 | 笔记 | 阅读启发 |
| --- | --- | --- | --- | --- | --- |
| 15 | [VideoMind: A Chain-of-LoRA Agent for Temporal-Grounded Video Reasoning](https://openreview.net/forum?id=57EwidOnSf) | 视频智能体、模块协作、LoRA | 待读 | 待创建：`videomind.md` | |
| 16 | [Time-R1: Post-Training Large Vision Language Model for Temporal Video Grounding](https://papers.neurips.cc/paper_files/paper/2025/hash/7801b29c93b599b8d0c44138596bdeed-Abstract-Conference.html) | 强化学习、可验证奖励、模型后训练 | 待读 | 待创建：`time_r1.md` | |


## 记录原则

- 每篇论文先完成“一句话总结”和“与本项目的关系”，再补充方法与实验细节。
- 结论只记录自己确认理解过的内容；不确定处明确标为“待确认”。
- 代码是否复现单独记录，不把“读懂论文”与“跑通代码”混为一件事。

