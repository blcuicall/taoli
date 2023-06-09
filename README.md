# 国际中文教育大模型

随着ChatGPT引起全社会的关注，及各类大语言模型（Large Language Model）争相亮相，通用领域自然语言处理任务已获得巨大成功，引起了国际中文教育领域的普遍关注。

国际中文教育人士纷纷展开了对大模型的探讨：
大模型是否可以根据学习者的水平，提供合适的语言表达，或根据学习者的问题给出详细的解答，从而在一定程度上辅助甚至充当学习伙伴、语言教师？
然而，目前通用领域的大模型在垂直领域的效果仍有限。

为解决上述问题，我们全面推出适用于国际中文教育领域的大模型 **“桃李”（Taoli）1.0** ，一个在国际中文教育领域数据上进行了额外训练的模型。

我们基于目前国际中文教育领域流通的500余册国际中文教育教材与教辅书、汉语水平考试试题以及汉语学习者词典等，构建了国际中文教育资源库。
我们设置了多种形式的指令来充分利用知识，构造了共计 88000 条的高质量国际中文教育问答数据集，并利用收集到的数据对模型进行指令微调，让模型习得将国际中文教育知识应用到具体场景中的能力。

---

本项目持续开展，国际中文教育领域数据集及系列模型后续相继开源，敬请关注。

**我们正在计划进行Taoli LLaMA 7B内测体验。如果你想体验我们的模型，请填写[此问卷](https://wenjuan.feishu.cn/m?t=sBpCKvr0G9Mi-k7yv)，我们将通过邮件联系您。**

## 新闻

[2023/6/8] 开源了基于目前国际中文教育领域流通的500余册国际中文教育教材与教辅书、汉语水平考试试题以及汉语学习者词典等，构建了国际中文教育资源库，其中包含9k语法改错数据4k释义生成数据、6k文本简化数据以及6k可控文本生成数据。

## 更新计划

- [ ] 发表 Taoli LLaMA 技术报告

- [ ] 开源更大规模的预训练数据

- [ ] 开源国际中文教育领域的指令微调数据

- [ ] 开源国际中文教育领域的预训练模型

- [ ] 开源通用教育领域的预训练模型

## 训练数据

### 通用指令微调数据

[Alpaca-GPT4](https://github.com/Instruction-Tuning-with-GPT-4/GPT-4-LLM) 52k 中文，52k 英文。

### 国际中文教育指令微调数据

#### 语法改错数据
我们使用汉语学习者文本多维标注数据集[YACLC](https://github.com/blcuicall/YACLC/tree/main/)的开发集作为语法改错中最小改动以及流利数据的来源，使用HSK作文评分数据作为篇章级语法改错的数据来源。

    Instruction:

    您是否能够帮助我修改下列文章中的语法错误，以确保其语法正确无误。

    Input:

    我最喜欢读的一本书我看过的书不少，但其中一本由琼瑶所著爱情小说《烟雨濛濛》却让我留下了深刻的印象，书中的男女主角刻骨铭心的爱情更令我流下了不少的眼泪，女主角因母亲在她很小的时候，遭到父亲的遗弃，因而产生了对父亲的仇视，也养生了她独立的性格。女主角因仇恨的缘故，报复心很强，起初用种种的方法抢走了她同父异母妹妹的男友，本来只是在报复，后来因为不知不觉真心爱上男主角，而在这时却被男主角误会他被利用而改选了她的妹妹。她痛心，她自责……而她父亲是一位枭雄，每一个人都必须服从他。性格顽强，不喜欢这个女儿而常常为难她，后来看见她性格却和他相似，而且这女儿，脾气虽然坏，但却很爱她妈妈，他被女儿尖酸刻薄的语言骂醒，不但原谅了她也认回了她妈妈。最后女主角和男主角也经过了很多的悲欢离合，在战火中等待的心情，在盼望归来形容中，每一句话，每一形容词都换了我不少的眼泪。由这本书中的人物描述，性格介绍，让我有如身在其中，因为在我一生中，也有遭到类似的爱情故事和家庭背景，但是我却没有男女主角的幸运有圆满的结果，但这本书却启发了我人生的目标，学习了独立的性格。

    Output:

    我最喜欢读的一本书我看过的书不少，但其中一本由琼瑶所著的爱情小说《烟雨濛濛》却让我留下了深刻的印象，书中的男女主角刻骨铭心的爱情更令我流下了不少的眼泪，女主角因母亲在她很小的时候，遭到父亲的遗弃，因而产生了对父亲的仇视，也养成了她独立的性格。女主角因仇恨的缘故，报复心很强，起初用种种的方法抢走了她同父异母妹妹的男友，本来只是在报复，后来不知不觉真心爱上了男主角，而在这时却被男主角误会他被利用而改选了她的妹妹。她痛心，她自责……而她父亲是一位枭雄，每一个人都必须服从他。性格顽强，不喜欢这个女儿而常常为难她，后来看见她性格却和他相似，而且这女儿，脾气虽然坏，但却很爱她妈妈，他被女儿尖酸刻薄的语言骂醒，不但原谅了她也认回了她妈妈。最后女主角和男主角也经过了很多的悲欢离合，在战火中等待的心情，在盼望归来用的形容时，每一句话，每一个形容词都换了我不少的眼泪。由这本书中的人物描述，性格介绍，让我有如身在其中，因为在我一生中，也有遇到类似的爱情故事和家庭背景，但是我却没有男女主角的幸运有圆满的结果，但这本书却启发了我人生的目标，学习了独立的性格。

#### 释义生成数据
我们从现代汉语词典和对外汉语词典中提取了大量词条用于释义数据的构建。

    Instruction:

    '因'在此上下文中的具体含义是什么？

    Input:

    济南因泉水而出名。

    Output:

    引出原因

#### 文本简化数据

我们使用多参考中文文本简化数据集 [Multi-Reference Chinese Text Simplification Dataset](https://github.com/blcuicall/mcts) 作为文本简化指令微调数据的来源。该数据集是迄今为止中文文本简化任务上规模最大、参考最多的评估数据集，包括 723 条从新闻语料中挑选的复杂结构句子，每一句分别包含多条人工简化后的句子。

    Instruction:

    请将这段话简化，使其适合非专业读者阅读。

    Input:

    没有系统的训练和足够的备战，球员的体能下降严重，伤病会增加，球迷在心理上也会有一个抵制ＮＢＡ的过程。

    Output:

    没有长时间的训练和足够的准备，球员的身体变差，容易受伤、生病，球迷会抵制ＮＢＡ。

#### 可控文本生成数据

我们采用汉语国际教育动态语料库（Corpus of Teaching Chinese as Second Language）作为数据来源。CTC 是一个以国际汉语教材文本语料为基础的语料库，旨在为汉语（二语）教与学双方提供数据驱动学习模式的语言资源，以及语言资源的智能检索。

    Instruction:

    请通过一个实例句子，向我展示'在'语法点在语法结构中的具体应用。

    Output:

    许多保姆都和主人住在一起，成了家庭生活中很重要的一个人。

## 模型参数

目前我们的Taoli LLaMA模型正在内测中：
* taoli-llama-7b-1.0: 以[Chinese-LLaMA-7B](https://github.com/ymcui/Chinese-LLaMA-Alpaca)，使用通用instruction和国际中文教育instruction数据进行指令微调。

欢迎通过[报名链接](https://wenjuan.feishu.cn/m?t=sBpCKvr0G9Mi-k7yv)填写内测报名问卷，我们将通过邮件与您进行联系。


## **系统效果**

我们选取了LLaMA 7B作为基座模型，在通用领域和国际中文教育领域指令微调。

以下对比了该模型和ChatGPT对于部分输入样例的回复：


**考试能力**

我们从教师与学习者两个方面出发，分别对几个模型在国际汉语教师资格证考试与汉语水平考试（HSK）上的表现进行了测评。其中HSK考试采用2018年官方出版的考试真题，从一级到六级各选择一套。国际汉语教师资格证考试采用2021年出版的官方真题。试题以客观题为主，主观题不参与计分。以HSK4-6级为例：

| **试题（客观题）** | **Taoli 1.0** | **GPT-4** |
| -- | -- | -- |
| HSK4 | 55 | 78 |
| HSK5 | 60 | 85 |
| HSK6 | 42 | 76 |

**样例展示**

| **输入** | **Taoli 1.0** |
| -- | -- |
| 请遵循最小改动原则纠正下面这句话：北京与西安有很多好象一样的地方。 | 北京和西安有很多类似的地方。|
| 请生成词语在当前上下文中的释义。<br>词语：折服 <br> 上下文：我深深地被他的奉献精神所折服。 | 被说服或被感动。 |
| 请使用下列所有词语，写一个30字左右的段落。<br>词语：元旦、放松、礼物、表演 | 元旦是一年中最重要的节日之一，人们会庆祝并享受放松的时间。在节日中，人们会收到礼物，表演，并享受各种活动。 |

## 合作单位

本项目由北京语言大学、清华大学、东北大学、北京交通大学合作完成。

## 致谢

本项目的开放过程中，获得了以下项目的帮助，在此表示感谢。

https://github.com/tatsu-lab/stanford_alpaca

https://github.com/ymcui/Chinese-LLaMA-Alpaca

## **局限性和使用限制**

本项目内容仅供用于学术研究，不得用于商业以及其他会对社会带来危害的用途。使用涉及第三方代码的部分时，请严格遵循相应的开源协议。模型生成的内容受模型计算、随机性和量化精度损失等因素影响，本项目无法对其准确性作出保证。

本项目中使用的部分数据由ChatGPT生成，未经严格验证，可能会存在错误内容，在使用时请注意甄别。

## 引用

如果您使用了本项目的内容，或者认为本项目对您的研究有帮助，请引用本项目。

```Plaintext

@misc{Taoli-LLama,
  author={Jingsi Yu and Junhui Zhu and Yujie Wang and Yang Liu and Hongxiang Chang and Jinran Nie and Cunliang Kong and Ruining Cong and XinLiu and Jiyuan An and Luming Lu and Mingwei Fang and Lin Zhu},
  title={Taoli Llama},
  year={2023},
  publisher={GitHub},
  journal={GitHub repository},
  howpublished={\url{https://github.com/blcuicall/taoli}},
}
```
