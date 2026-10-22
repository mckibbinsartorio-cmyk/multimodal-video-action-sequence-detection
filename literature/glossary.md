# 领域术语表

> 用于记录“多模态大模型 + 视频理解 + 动作序列检测”方向的专用名词。  
> 新术语首次出现时先记录英文名、中文名和自己的理解；不确定的解释标注“待确认”。

| 英文简称 | 具体英文名 | 中文名 | 详细解释 |
| --- | --- | --- | --- |
| LLM | Large Language Model | 大语言模型 | 以大量文本数据训练的语言模型，能够理解和生成自然语言。在视频任务中，通常负责理解用户问题并生成回答。 |
| MLLM | Multimodal Large Language Model | 多模态大语言模型 | 能够联合处理文本、图像、音频或视频等多种模态信息的大语言模型。 |
| VidLLM | Video Large Language Model | 视频大语言模型 | 以视频理解为主要能力或输入形式的大语言模型，通常由视频编码器和 LLM 组成。 |
| VLM | Vision-Language Model | 视觉语言模型 | 联合学习视觉信息与语言信息的模型；可处理图像或视频与文本之间的对应关系。 |
| Token | Token | 词元 / 标记 | 模型进行计算时使用的基本表示单位。文本可被切分为文本 token；图像或视频也会被编码成视觉 token。 |
| Visual Token | Visual Token | 视觉标记 | 图像帧或视频片段经过视觉编码器后得到的向量表示，供语言模型进一步理解。 |
| Video Encoder | Video Encoder | 视频编码器 | 将原始视频帧转换为模型可处理特征或视觉 token 的模块。 |
| Timestamp | Timestamp | 时间戳 | 表示视频中某一帧或事件发生时间的信息，例如“12.5 秒”。 |
| Temporal Localization | Temporal Localization | 时间定位 | 判断某个事件或动作在视频中发生的具体时间点或时间区间。 |
| Temporal Grounding | Temporal Grounding | 时间视频定位 / 时序定位 | 根据语言查询，在视频中找出对应事件的起止时间区间。 |
| Dense Video Captioning | Dense Video Captioning | 密集视频描述 | 对视频中的多个事件分别生成描述，并通常同时给出各事件的时间区间。 |
| Highlight Detection | Highlight Detection | 高光片段检测 | 从视频中识别最重要、最精彩或最符合某一需求的片段。 |
| Instruction Tuning | Instruction Tuning | 指令微调 | 使用“指令 - 输入 - 回答”形式的数据继续训练模型，使其更能遵循用户指令。 |
| Q-Former | Querying Transformer | 查询 Transformer | 通过一组可学习查询向量，从视觉特征中提取并压缩对语言模型有用信息的模块。 |
| Sliding Video Q-Former | Sliding Video Q-Former | 滑动视频 Q-Former | TimeChat 使用的模块：以滑动窗口依次处理视频片段，生成可随视频长度变化的视频 token 序列。 |
| Time-aware Frame Encoder | Time-aware Frame Encoder | 时间感知帧编码器 | TimeChat 使用的模块：将单帧视觉内容与该帧时间戳显式关联，以增强模型的时间理解能力。 |
| Zero-shot | Zero-shot Learning | 零样本学习 | 模型在没有针对某个目标任务或数据集进行专门训练的情况下，直接完成该任务的能力。 |
