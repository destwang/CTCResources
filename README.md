[**English**](https://github.com/destwang/CTCResources) | [**中文**](https://github.com/destwang/CTCResources/blob/main/README_ZH.md)

# CTCResources

Resources for Chinese text correction (CTC). The resource list is mainly mantained by Baoxin Wang and Honghong Zhao from HFL (哈工大讯飞联合实验室).

## Contents

- [CTCResources](#ctcresources)
  - [Contents](#contents)
  - [Defination](#defination)
    - [Chinese Spelling Check (CSC)](#chinese-spelling-check-csc)
    - [Grammatical Error Correction (GEC)](#grammatical-error-correction-gec)
  - [Experimental Results on Public Datasets](#experimental-results-on-public-datasets)
    - [SIGHAN 2015](#sighan-2015)
  - [Papers](#papers)
    - [CSC Papers](#csc-papers)
    - [GEC Papers](#gec-papers)
  - [Datasets](#datasets)
    - [CTC 2021 :](#ctc-2021-)
    - [Others:](#others)
  - [Systems & API](#systems--api)
  - [Other Resources](#other-resources)
    - [Related Articles](#related-articles)
    - [Shared Task](#shared-task)
  - [* CTC 2021](#-ctc-2021)


## Defination
### Chinese Spelling Check (CSC)
Chinese  spelling  check  (CSC)  is  a  task  to detect  and  correct  spelling  errors  in  Chinese text.

### Grammatical Error Correction (GEC)
Grammatical Error Correction (GEC) is the task of correcting different kinds of errors in text such as spelling, punctuation, grammatical, and word choice errors.

## Experimental Results on Public Datasets
### SIGHAN 2015
*We have not collected the character-level results because of some bugs in the current commonly used character-level evaluation script. It is also recommended that researchers **do not** use character-level evaluation script or fix the evaluation script before using it.*

* Without Pretraining 

| Model | D-P | D-R | D-F | C-P | C-R | C-F |
| - | - | - | - | - | - | - |
| [FASPell](https://github.com/iqiyi/FASPell) | 67.6 | 60.0 | 63.5 | 66.6 | 59.1 | 62.6 |
| BERT | 73.7 | 78.2 | 75.9 | 70.9 | 75.2 | 73.0 |
| RoBERTa | 74.7 | 77.3 | 76.0 | 72.1 | 74.5 | 73.3 |
| [SpellGCN](https://github.com/ACL2020SpellGCN/SpellGCN) | 74.8 | **80.7** | 77.7 | 72.1 | **77.7** | 74.8 (75.9) |
| [DCN](https://github.com/destwang/DCN) | **76.6** | 79.8 | **78.2** | **74.2** | 77.3 | **75.7** |

* With Pretraining

| Model | D-P | D-R | D-F | C-P | C-R | C-F |
| - | - | - | - | - | - | - |
| [BERT_CRS + GAD](https://aclanthology.org/2021.findings-acl.122.pdf) | 75.6 | 80.4 | 77.9 | 73.2 | 77.8 | 75.4 |
| [DCN-pretrain](https://github.com/destwang/DCN) | 77.1 | 80.9 | 79.0 | 74.5 | 78.2 | 76.3 |
| [REALISE](https://github.com/DaDaMrX/ReaLiSe) | 77.3 | 81.3 | 79.3 | 75.9 | 79.9 | **77.8** |
| [PLOME](https://github.com/liushulinle/PLOME) | 77.4 | 81.5 | 79.4 | 75.3 | 79.3 | 77.2 |
| [Soft-Masked BERT](https://aclanthology.org/2020.acl-main.82.pdf) | 73.7 | 73.2 | 73.5 | 66.7 | 66.2 | 66.4 |
| [Soft-Masked BERT_SSCL](https://aclanthology.org/2021.emnlp-main.281.pdf) | **86.3** | 72.5 | 78.8 | **85.2** | 66.0 | 74.4 |
| [MLM-phonetics](https://aclanthology.org/2021.findings-acl.198.pdf) | 77.5 | **83.1** | **80.2** | 74.9 | **80.2** | 77.5 |

## Papers
### CSC Papers
> ### 2022
**MDCSpell: A Multi-task Detector-Corrector Framework for Chinese Spelling Correction**. Findings of ACL 2022.  
Chenxi Zhu, Ziqiang Ying, Boyu Zhang, Feng Mao. [[pdf](https://aclanthology.org/2022.findings-acl.98/)]

**CRASpell: A Contextual Typo Robust Approach to Improve Chinese Spelling Correction**. Findings of ACL 2022.  
Shulin Liu, Shengkang Song, Tianchi Yue, Tao Yang, Huihui Cai, TingHao Yu, Shengli Sun. [[pdf](https://aclanthology.org/2022.findings-acl.237/)]

**The Past Mistake is the Future Wisdom: Error-driven Contrastive Probability Optimization for Chinese Spell Checking**.  Findings of ACL 2022.  
Yinghui Li, Qingyu Zhou, Yangning Li, Zhongli Li, Ruiyang Liu, Rongyi Sun, Zizhen Wang, Chao Li, Yunbo Cao, Hai-Tao Zheng. [[pdf](https://aclanthology.org/2022.findings-acl.252/)]

> ### 2021
**PLOME: Pre-training with Misspelled Knowledge for Chinese Spelling Correction**. ACL 2021.  
Shulin Liu, Tao Yang, Tianchi Yue, Feng Zhang and Di Wang. [[pdf](https://aclanthology.org/2021.acl-long.233.pdf)], [[code](https://github.com/liushulinle/PLOME)].

**PHMOSpell: Phonological and Morphological Knowledge Guided Chinese Spelling Check**. ACL 2021.  
Li Huang, Junjie Li, Weiwei Jiang, Zhiyu Zhang, Minchuan Chen, Shaojun Wang and Jing Xiao. [[pdf](https://aclanthology.org/2021.acl-long.464.pdf)].

**Exploration and Exploitation: Two Ways to Improve Chinese Spelling Correction Models**. ACL 2021.  
Chong Li, Cenyuan Zhang, Xiaoqing Zheng and Xuanjing Huang. [[pdf](https://arxiv.org/pdf/2105.14813.pdf)], [[code](https://github.com/FDChongli/TwoWaysToImproveCSC)].

**Dynamic Connected Networks for Chinese Spelling Check**. Findings of ACL 2021.  
Baoxin Wang, Wanxiang Che, Dayong Wu, Shijin Wang, Guoping Hu and Ting Liu. [[pdf](https://aclanthology.org/2021.findings-acl.216.pdf)], [[code](https://github.com/destwang/DCN)].

**Read, Listen, and See: Leveraging Multimodal Information Helps Chinese Spell Checking**. Findings of ACL 2021.  
Heng-Da Xu, Zhongli Li, Qingyu Zhou, Chao Li, Zizhen Wang, Yunbo Cao, Heyan Huang and Xian-Ling Mao. [[pdf](https://arxiv.org/pdf/2105.12306.pdf)], [[code](https://github.com/DaDaMrX/ReaLiSe)].

**Global Attention Decoder for Chinese Spelling Error Correction**. Findings of ACL 2021.  
Zhao Guo, Yuan Ni, Keqiang Wang, Wei Zhu and Guotong Xie. [[pdf](https://aclanthology.org/2021.findings-acl.122.pdf)].

**Correcting Chinese Spelling Errors with Phonetic Pre-training**. Findings of ACL 2021.  
Ruiqing Zhang, Chao Pang, Chuanqiang Zhang, Shuohuan Wang, Zhongjun He, Yu Sun, Hua Wu and Haifeng Wang. [[pdf](https://aclanthology.org/2021.findings-acl.198.pdf)].

**DCSpell: A Detector-Corrector Framework for Chinese Spelling Error Correction**. SIGIR 2021.  
Jing Li, Gaosheng Wu, Dafei Yin, Haozhao Wang, Yonggang Wang. [[pdf](https://dl.acm.org/doi/pdf/10.1145/3404835.3463050)].

**SpellBERT: A Lightweight Pretrained Model for Chinese Spelling Check**. EMNLP 2021.  
Tuo Ji, Hang Yan, Xipeng Qiu. [[pdf](https://aclanthology.org/2021.emnlp-main.287.pdf)].

**Self-Supervised Curriculum Learning for Spelling Error Correction**. EMNLP 2021.  
Zifa Gan, Hongfei Xu, Hongying Zan. [[pdf](https://aclanthology.org/2021.emnlp-main.281.pdf)].

**An Alignment-Agnostic Model for Chinese Text Error Correction**. Findings of EMNLP 2021.  
Liying Zheng, Yue Deng, Weishun Song, Liang Xu and Jing Xiao. [[pdf](https://aclanthology.org/2021.findings-emnlp.30.pdf)].

**Domain-Shift Conditioning Using Adaptable Filtering Via Hierarchical Embeddings for Robust Chinese Spell Check**. TASLP 2021.  
Minh Nguyen, Gia H. Ngo, and Nancy F. Chen. [[pdf](https://ieeexplore.ieee.org/abstract/document/9439969)].

> ### 2020
**Chunk-based Chinese Spelling Check with Global Optimization**. Findings of EMNLP 2020.  
Zuyi Bao, Chen Li and Rui Wang. [[pdf](https://aclanthology.org/2020.findings-emnlp.184.pdf)].

**SpellGCN: Incorporating Phonological and Visual Similarities into Language Models for Chinese Spelling Check**. ACL 2020.  
Xingyi Cheng, Weidi Xu, Kunlong Chen, Shaohua Jiang, Feng Wang, Taifeng Wang, Wei Chu and Yuan Qi. [[pdf](https://aclanthology.org/2020.acl-main.81.pdf)], [[code](https://github.com/ACL2020SpellGCN/SpellGCN)].

**Spelling Error Correction with Soft-Masked BERT**. ACL 2020.  
Shaohua Zhang, Haoran Huang, Jicong Liu and Hang Li. [[pdf](https://aclanthology.org/2020.acl-main.82.pdf)].

> ### 2019
**FASPell: A Fast, Adaptable, Simple, Powerful Chinese Spell Checker Based On DAE-Decoder Paradigm**. EMNLP 2019 Workshop W-NUT.  
Yuzhong Hong, Xianguo Yu, Neng He, Nan Liu, Junhui Liu. [[pdf](https://aclanthology.org/D19-5522.pdf)], [[code](https://github.com/iqiyi/FASPell)].

**Confusionset-guided Pointer Networks for Chinese Spelling Check**. ACL 2019.  
Dingmin Wang, Yi Tay, Li Zhong. [[pdf](https://aclanthology.org/P19-1578.pdf)], [[code](https://github.com/sunnyqiny/Confusionset-guided-Pointer-Networks-for-Chinese-Spelling-Check)].

### GEC Papers
> ### 2022

**Ensembling and Knowledge Distilling of Large Sequence Taggers for Grammatical Error Correction**. ACL 2022.  
Maksym Tarnavskyi, Artem Chernodub, Kostiantyn Omelianchuk. [[pdf](https://aclanthology.org/2022.acl-long.266/)]

**Interpretability for Language Learners Using Example-Based Grammatical Error Correction**. ACL 2022.  
Masahiro Kaneko, Sho Takase, Ayana Niwa, Naoaki Okazaki. [[pdf](https://aclanthology.org/2022.acl-long.496/)]

**Adjusting the Precision-Recall Trade-Off with Align-and-Predict Decoding for Grammatical Error Correction**. ACL 2022 short.  
Xin Sun, Houfeng Wang. [[pdf](https://aclanthology.org/2022.acl-short.77/)]

**“Is Whole Word Masking Always Better for Chinese BERT?”: Probing on Chinese Grammatical Error Correction**. Findings of ACL 2022.  
Yong Dai, Linyang Li, Cong Zhou, Zhangyin Feng, Enbo Zhao, Xipeng Qiu, Piji Li, Duyu Tang. [[pdf](https://aclanthology.org/2022.findings-acl.1/)]

**Type-Driven Multi-Turn Corrections for Grammatical Error Correction**. Findings of ACL 2022.  
Shaopeng Lai, Qingyu Zhou, Jiali Zeng, Zhongli Li, Chao Li, Yunbo Cao, Jinsong Su. [[pdf](https://aclanthology.org/2022.findings-acl.254/)]

**Reusing a Multi-lingual Setup to Bootstrap a Grammar Checker for a Very Low Resource Language without Data**. ComputEL 2022 Workshop.  
Inga Lill Sigga Mikkelsen, Linda Wiechetek, Flammie A Pirinen. [[pdf](https://aclanthology.org/2022.computel-1.19/)]

> ### 2021

**Instantaneous Grammatical Error Correction with Shallow Aggressive Decoding**. ACL 2021.  
Xin Sun, Tao Ge, Furu Wei, Houfeng Wang.[[pdf](https://aclanthology.org/2021.acl-long.462/)].[[code](https://github.com/AutoTemp/Shallow-Aggressive-Decoding)].

**Tail-to-Tail Non-Autoregressive Sequence Prediction for Chinese Grammatical ErrorCorrection**. ACL 2021.  
Piji Li, Shuming Shi.[[pdf](https://aclanthology.org/2021.acl-long.385/)].[[code](https://github.com/lipiji/TtT)].

**A Simple Recipe for Multilingual Grammatical Error Correction**. ACL 2021 short.  
Sascha Rothe, Jonathan Mallinson, Eric Malmi, Sebastian Krause, Aliaksei Severyn.[[pdf](https://aclanthology.org/2021.acl-short.89/)].

**Synthetic Data Generation for Grammatical Error Correction with Tagged Corruption Models**. EACL-BEA 2021.  
Felix Stahlberg, Shankar Kumar.[[pdf](https://aclanthology.org/2021.bea-1.4/)].

**Document-level grammatical error correction**. EACL-BEA 2021.  
Zheng Yuan, Christopher Bryant.[[pdf](https://aclanthology.org/2021.bea-1.8/)].

**Data Strategies for Low-Resource Grammatical Error Correction**. EACL-BEA 2021.  
Simon Flachs, Felix Stahlberg, Shankar Kumar.[[pdf](https://aclanthology.org/2021.bea-1.12/)].

**Assessing Grammatical Correctness in Language Learning**. EACL-BEA 2021.  
Anisia Katinskaia, Roman Yangarber.[[pdf](https://aclanthology.org/2021.bea-1.15/)].

**Neural Quality Estimation with Multiple Hypotheses for Grammatical Error Correction**. NAACL2021.  
Zhenghao Liu, Xiaoyuan Yi, Maosong Sun, Liner Yang, Tat-Seng Chua.[[pdf](https://aclanthology.org/2021.naacl-main.429/)].

**Comparison of Grammatical Error Correction Using Back-Translation Models**. NAACL2021 workshop.  
Aomi Koyama, Kengo Hotate, Masahiro Kaneko, Mamoru Komachi.[[pdf](https://aclanthology.org/2021.naacl-srw.16/)].

**LM-Critic: Language Models for Unsupervised Grammatical Error Correction**. EMNLP 2021.  
Michihiro Yasunaga, Jure Leskovec and Percy Liang.[[pdf](https://arxiv.org/abs/2109.06822)].

**Multi-Class Grammatical Error Detection for Correction: A Tale of Two Systems**. EMNLP 2021.  
Zheng Yuan, Shiva Taslimipoor, Christopher Davis and Christopher Bryant.

> ### 2020

**On the Robustness of Language Encoders against Grammatical Errors**. ACL 2020.  
Fan Yin, Quanyu Long, Tao Meng, Kai-Wei Chang.[[pdf](https://aclanthology.org/2020.acl-main.310/)].

**Encoder-Decoder Models Can Benefit from Pre-trained Masked Language Models in Grammatical Error Correction**. ACL 2020.  
Masahiro Kaneko, Masato Mita, Shun Kiyono, Jun Suzuki, Kentaro Inui.[[pdf](https://aclanthology.org/2020.acl-main.391/)].

**Grammatical Error Correction Using Pseudo Learner Corpus Considering Learner’s Error Tendency**. ACL 2020 workshop.  
Yujin Takahashi, Satoru Katsumata, Mamoru Komachi.[[pdf](https://aclanthology.org/2020.acl-srw.5/)].

**GECToR – Grammatical Error Correction: Tag, Not Rewrite**. ACL-BEA 2020.  
Kostiantyn Omelianchuk, Vitaliy Atrasevych, Artem Chernodub, Oleksandr Skurzhanskyi.[[pdf](https://aclanthology.org/2020.bea-1.16/)].

**A Comparative Study of Synthetic Data Generation Methods for Grammatical Error Correction**. ACL-BEA 2020.  
Max White, Alla Rozovskaya.[[pdf](https://aclanthology.org/2020.bea-1.21/)].

**Improving Grammatical Error Correction Models with Purpose-Built Adversarial Examples**. EMNLP 2020.  
Lihao Wang, Xiaoqing Zheng.[[pdf](https://aclanthology.org/2020.emnlp-main.228/)].

**Improving the Efficiency of Grammatical Error Correction with Erroneous Span Detection and Correction**. EMNLP 2020.  
Mengyun Chen, Tao Ge, Xingxing Zhang, Furu Wei, Ming Zhou.[[pdf](https://aclanthology.org/2020.emnlp-main.581/)].

**Grammatical Error Correction in Low Error Density Domains: A New Benchmark and Analyses**. EMNLP 2020.  
Simon Flachs, Ophélie Lacroix, Helen Yannakoudakis, Marek Rei, Anders Søgaard.[[pdf](https://aclanthology.org/2020.emnlp-main.680/)].

**Adversarial Grammatical Error Correction**. findings of EMNLP 2020 .  
Vipul Raheja, Dimitris Alikaniotis.[[pdf](https://aclanthology.org/2020.findings-emnlp.275/)].

**A Self-Refinement Strategy for Noise Reduction in Grammatical Error Correction**. findings of EMNLP 2020 .  
Masato Mita, Shun Kiyono, Masahiro Kaneko, Jun Suzuki, Kentaro Inui.[[pdf](https://aclanthology.org/2020.findings-emnlp.26/)].

**Improving Grammatical Error Correction with Machine Translation Pairs**. findings of EMNLP 2020 .  
Wangchunshu Zhou, Tao Ge, Chang Mu, Ke Xu, Furu Wei, Ming Zhou.[[pdf](https://aclanthology.org/2020.findings-emnlp.30/)].

**Chinese Grammatical Correction Using BERT-based Pre-trained Model**. AACL 2020.  
Hongfei Wang, Michiki Kurosawa, Satoru Katsumata, Mamoru Komachi.[[pdf](https://aclanthology.org/2020.aacl-main.20/)].

**Stronger Baselines for Grammatical Error Correction Using a Pretrained Encoder-Decoder Model**. AACL 2020.  
Satoru Katsumata, Mamoru Komachi.[[pdf](https://aclanthology.org/2020.aacl-main.83/)].

**Generating Diverse Corrections with Local Beam Search for Grammatical Error Correction**. COLING 2020.  
Kengo Hotate, Masahiro Kaneko, Mamoru Komachi.[[pdf](https://aclanthology.org/2020.coling-main.193/)].

**Heterogeneous Recycle Generation for Chinese Grammatical Error Correction**. COLING 2020.  
Charles Hinson, Hen-Hsen Huang, Hsin-Hsi Chen.[[pdf](https://aclanthology.org/2020.coling-main.199/)].

**Improving Grammatical Error Correction with Data Augmentation by Editing Latent Representation**. COLING 2020.  
Zhaohong Wan, Xiaojun Wan, Wenguang Wang.[[pdf](https://aclanthology.org/2020.coling-main.200/)].

**Cross-lingual Transfer Learning for Grammatical Error Correction**. COLING 2020.  
Ikumi Yamashita, Satoru Katsumata, Masahiro Kaneko, Aizhan Imankulova,Mamoru Komachi.[[pdf](https://aclanthology.org/2020.coling-main.415/)].

> ### 2019

**Cross-Sentence Grammatical Error Correction**. ACL 2019.  
Shamil Chollampatt, Weiqi Wang, Hwee Tou Ng.[[pdf](https://aclanthology.org/P19-1042/)].

**Automatic Grammatical Error Correction for Sequence-to-sequence Text Generation: An Empirical Study**. ACL 2019.  
Tao Ge, Xingxing Zhang, Furu Wei, Ming Zhou.[[pdf](https://aclanthology.org/P19-1609/)].

**Controlling Grammatical Error Correction Using Word Edit Rate**. ACL 2019.  
Kengo Hotate, Masahiro Kaneko, Satoru Katsumata, Mamoru Komachi.[[pdf](https://aclanthology.org/P19-2020/)].

**Context is Key: Grammatical Error Detection with Contextual Word Representations**. ACL-BEA 2019.  
Samuel Bell, Helen Yannakoudakis, Marek Rei.[[pdf](https://aclanthology.org/W19-4410/)].

**The Unreasonable Effectiveness of Transformer Language Models in Grammatical Error Correction**. ACL-BEA 2019.  
Dimitris Alikaniotis, Vipul Raheja.[[pdf](https://aclanthology.org/W19-4412/)].

**(Almost) Unsupervised Grammatical Error Correction using Synthetic Comparable Corpus**. ACL-BEA 2019.  
Satoru Katsumata, Mamoru Komachi.[[pdf](https://aclanthology.org/W19-4413/)].

**Learning to combine Grammatical Error Corrections**. ACL-BEA 2019.  
Yoav Kantor, Yoav Katz, Leshem Choshen, Edo Cohen-Karlik, Naftali Liberman, Assaf Toledo, Amir Menczel, Noam Slonim.[[pdf](https://aclanthology.org/W19-4414/)].

**Erroneous data generation for Grammatical Error Correction**. ACL-BEA 2019.  
Shuyao Xu, Jiehao Zhang, Jin Chen, Long Qin.[[pdf](https://aclanthology.org/W19-4415/)].

**The CUED’s Grammatical Error Correction Systems for BEA-2019**. ACL-BEA 2019.  
Felix Stahlberg, Bill Byrne.[[pdf](https://aclanthology.org/W19-4417/)].

**CUNI System for the Building Educational Applications 2019 Shared Task: Grammatical Error Correction**. ACL-BEA 2019.  
Jakub Náplava, Milan Straka.[[pdf](https://aclanthology.org/W19-4419/)].

**Noisy Channel for Low Resource Grammatical Error Correction**. ACL-BEA 2019.  
Simon Flachs, Ophélie Lacroix, Anders Søgaard.[[pdf](https://aclanthology.org/W19-4420/)].

**TMU Transformer System Using BERT for Re-ranking at BEA 2019 Grammatical Error Correction on Restricted Track**. ACL-BEA 2019.  
Masahiro Kaneko, Kengo Hotate, Satoru Katsumata, Mamoru Komachi.[[pdf](https://aclanthology.org/W19-4422/)].

**A Neural Grammatical Error Correction System Built On Better Pre-training and Sequential Transfer Learning**. ACL-BEA 2019.  
Yo Joong Choe, Jiyeon Ham, Kyubyong Park, Yeoil Yoon.[[pdf](https://aclanthology.org/W19-4423/)].

**Neural and FST-based approaches to grammatical error correction**. ACL-BEA 2019.  
Zheng Yuan, Felix Stahlberg, Marek Rei, Bill Byrne, Helen Yannakoudakis.[[pdf](https://aclanthology.org/W19-4424/)].

**Improving Precision of Grammatical Error Correction with a Cheat Sheet**. ACL-BEA 2019.  
Mengyang Qiu, Xuejiao Chen, Maggie Liu, Krishna Parvathala, Apurva Patil, Jungyeul Park.[[pdf](https://aclanthology.org/W19-4425/)].

**Multi-headed Architecture Based on BERT for Grammatical Errors Correction**. ACL-BEA 2019.  
Bohdan Didenko, Julia Shaptala.[[pdf](https://aclanthology.org/W19-4426/)].

**Neural Grammatical Error Correction Systems with Unsupervised Pre-training on Synthetic Data**. ACL-BEA 2019.  
Roman Grundkiewicz, Marcin Junczys-Dowmunt, Kenneth Heafield.[[pdf](https://aclanthology.org/W19-4427/)].

**The Unbearable Weight of Generating Artificial Errors for Grammatical Error Correction**. ACL-BEA 2019.  
Phu Mon Htut, Joel Tetreault.[[pdf](https://aclanthology.org/W19-4449/)].

**An Empirical Study of Incorporating Pseudo Data into Grammatical Error Correction**. EMNLP 2019.  
Shun Kiyono, Jun Suzuki, Masato Mita, Tomoya Mizumoto, Kentaro Inui.[[pdf](https://arxiv.org/abs/1909.00502)].

**Encode, Tag, Realize: High-Precision Text Editing**. EMNLP 2019.  
Eric Malmi, Sebastian Krause, Sascha Rothe, Daniil Mirylenka, Aliaksei Severyn.[[pdf](https://aclanthology.org/D19-1510/)].

**Personalizing Grammatical Error Correction: Adaptation to Proficiency Level and L1**. EMNLP 2019.  
Maria Nadejde, Joel Tetreault.[[pdf](https://aclanthology.org/D19-5504/)].

**Grammatical Error Correction in Low-Resource Scenarios**. EMNLP 2019.  
Jakub Náplava, Milan Straka.[[pdf](https://aclanthology.org/D19-5545/)].

**Minimally-Augmented Grammatical Error Correction**. EMNLP 2019.  
Roman Grundkiewicz, Marcin Junczys-Dowmunt.[[pdf](https://aclanthology.org/D19-5546/)].

**Parallel Iterative Edit Models for Local Sequence Transduction**. EMNLP 2019.  
Abhijeet Awasthi, Sunita Sarawagi, Rasna Goyal, Sabyasachi Ghosh, Vihari Piratla.[[pdf](https://aclanthology.org/D19-1435/)].

**Learning to Copy for Automatic Post-Editing**. EMNLP 2019.  
Xuancheng Huang, Yang Liu, Huanbo Luan, Jingfang Xu, Maosong Sun.[[pdf](https://aclanthology.org/D19-1634/)].

**Improving Grammatical Error Correction via Pre-Training a Copy-Augmented Architecture with Unlabeled Data**. NAACL 2019.  
Wei Zhao, Liang Wang, Kewei Shen, Ruoyu Jia, Jingming Liu.[[pdf](https://aclanthology.org/N19-1014/)].

**Cross-Corpora Evaluation and Analysis of Grammatical Error Correction Models — Is Single-Corpus Evaluation Enough?**. NAACL 2019.  
Masato Mita, Tomoya Mizumoto, Masahiro Kaneko, Ryo Nagata, Kentaro Inui.[[pdf](https://aclanthology.org/N19-1132/)].

**Corpora Generation for Grammatical Error Correction**. NAACL 2019.  
Jared Lichtarge, Chris Alberti, Shankar Kumar, Noam Shazeer, Niki Parmar, Simon Tong.[[pdf](https://aclanthology.org/N19-1333/)].

**Neural Grammatical Error Correction with Finite State Transducers**. NAACL 2019.  
Felix Stahlberg, Christopher Bryant, Bill Byrne.[[pdf](https://aclanthology.org/N19-1406/)].

> ### 2018

**Inherent Biases in Reference-based Evaluation for Grammatical Error Correction**. ACL 2018.  
Leshem Choshen, Omri Abend.[[pdf](https://aclanthology.org/P18-1059/)].

**Fluency Boost Learning and Inference for Neural Grammatical Error Correction**. ACL 2018.  
Tao Ge, Furu Wei, Ming Zhou.[[pdf](https://aclanthology.org/P18-1097/)].

**Automatic Metric Validation for Grammatical Error Correction**. ACL 2018.  
Leshem Choshen, Omri Abend.[[pdf](https://aclanthology.org/P18-1127/)].

**Overview of NLPTEA-2018 Share Task Chinese Grammatical Error Diagnosis**. ACL 2018 NLPTEA.  
Gaoqi Rao, Qi Gong, Baolin Zhang, Endong Xun.[[pdf](https://aclanthology.org/W18-3706/)].

**Approaching Neural Grammatical Error Correction as a Low-Resource Machine Translation Task**. NAACL 2018.  
Marcin Junczys-Dowmunt, Roman Grundkiewicz, Shubha Guha, Kenneth Heafield.[[pdf](https://aclanthology.org/N18-1055/)].

**Noising and Denoising Natural Language: Diverse Backtranslation for Grammar Correction**. NAACL 2018.  
Ziang Xie, Guillaume Genthial, Stanley Xie, Andrew Ng, Dan Jurafsky.[[pdf](https://aclanthology.org/N18-1057/)].

**Reference-less Measure of Faithfulness for Grammatical Error Correction**. NAACL 2018 short.  
Leshem Choshen, Omri Abend.[[pdf](https://aclanthology.org/N18-2020/)].

**Near Human-Level Performance in Grammatical Error Correction with Hybrid Machine Translation**. NAACL 2018 short.  
Roman Grundkiewicz, Marcin Junczys-Dowmunt.[[pdf](https://aclanthology.org/N18-2046/)].

**Language Model Based Grammatical Error Correction without Annotated Training Data**. NAACL 2018 BEA.  
Christopher Bryant, Ted Briscoe.[[pdf](https://aclanthology.org/W18-0529/)].

**A Multilayer Convolutional Encoder-Decoder Neural Network for Grammatical Error Correction**. AAAI 2018.  
Shamil Chollampatt, Hwee Tou Ng.[[pdf](https://www.aaai.org/ocs/index.php/AAAI/AAAI18/paper/viewFile/17308/16137)].

**Neural Quality Estimation of Grammatical Error Correction**. EMNLP 2018.  
Shamil Chollampatt, Hwee Tou Ng.[[pdf](https://aclanthology.org/D18-1274/)].

**Wronging a Right: Generating Better Errors to Improve Grammatical Error Detection**. EMNLP 2018.  
Sudhanshu Kasewa, Pontus Stenetorp, Sebastian Riedel.[[pdf](https://aclanthology.org/D18-1541/)].

**Using Wikipedia Edits in Low Resource Grammatical Error Correction**. EMNLP 2018.  
Adriane Boyd.[[pdf](https://aclanthology.org/W18-6111/)].

**Cool English: a Grammatical Error Correction System Based on Large Learner Corpora**. COLING 2018.  
Yu-Chun Lo, Jhih-Jie Chen, Chingyu Yang, Jason Chang.[[pdf](https://aclanthology.org/C18-2018/)].

**A Reassessment of Reference-Based Grammatical Error Correction Metrics**. COLING 2018.  
Shamil Chollampatt, Hwee Tou Ng.[[pdf](https://aclanthology.org/C18-1231/)].

> ### earlier

**A Nested Attention Neural Hybrid Model for Grammatical Error Correction**. ACL 2017.  
Jianshu Ji, Qinlong Wang, Kristina Toutanova, Yongen Gong, Steven Truong, Jianfeng Gao.[[pdf](https://aclanthology.org/P17-1070/)].

**Automatic Annotation and Evaluation of Error Types for Grammatical Error Correction**. ACL 2017.  
Christopher Bryant, Mariano Felice, Ted Briscoe.[[pdf](https://aclanthology.org/P17-1074/)].

**Neural Sequence-Labelling Models for Grammatical Error Correction**. EMNLP 2017.  
Helen Yannakoudakis, Marek Rei, Øistein E. Andersen, Zheng Yuan.[[pdf](https://aclanthology.org/D17-1297/)].

**JFLEG: A Fluency Corpus and Benchmark for Grammatical Error Correction**. EACL 2017.  
Courtney Napoles, Keisuke Sakaguchi, Joel Tetreault.[[pdf](https://aclanthology.org/E17-2037/)].

**Grammatical Error Detection Using Error- and Grammaticality-Specific Word Embeddings**. IJCNLP 2017.  
Masahiro Kaneko, Yuya Sakaizawa, Mamoru Komachi.[[pdf](https://aclanthology.org/I17-1005/)].

**Reference-based Metrics can be Replaced with Reference-less Metrics in Evaluating Grammatical Error Correction Systems**. IJCNLP 2017.  
Hiroki Asano, Tomoya Mizumoto, Kentaro Inui.[[pdf](https://aclanthology.org/I17-2058/)].

**Grammatical Error Correction with Neural Reinforcement Learning**. IJCNLP 2017.  
Keisuke Sakaguchi, Matt Post, Benjamin Van Durme.[[pdf](https://aclanthology.org/I17-2062/)].

**Grammatical Error Correction: Machine Translation and Classifiers**. ACL 2016.  
Alla Rozovskaya, Dan Roth.[[pdf](https://aclanthology.org/P16-1208/)].

**Compositional Sequence Labeling Models for Error Detection in Learner Writing**. ACL 2016.  
Marek Rei, Helen Yannakoudakis.[[pdf](https://aclanthology.org/P16-1112/)].

**Grammatical error correction using neural machine translation**. NAACL 2016 short.  
Zheng Yuan, Ted Briscoe.[[pdf](https://aclanthology.org/N16-1042/)].

**Discriminative Reranking for Grammatical Error Correction with Statistical Machine Translation**. NAACL 2016 short.  
Tomoya Mizumoto, Yuji Matsumoto.[[pdf](https://aclanthology.org/N16-1133/)].

**Phrase-based Machine Translation is State-of-the-Art for Automatic Grammatical Error Correction**. EMNLP 2016.  
Marcin Junczys-Dowmunt, Roman Grundkiewicz.[[pdf](https://aclanthology.org/D16-1161/)].

**Adapting Grammatical Error Correction Based on the Native Language of Writers with Neural Network Joint Models**. EMNLP 2016.  
Shamil Chollampatt, Duc Tam Hoang, Hwee Tou Ng.[[pdf](https://aclanthology.org/D16-1195/)].

**There’s No Comparison: Reference-less Evaluation Metrics in Grammatical Error Correction**. EMNLP 2016.  
Courtney Napoles, Keisuke Sakaguchi, Joel Tetreault.[[pdf](https://aclanthology.org/D16-1228/)].

**Chinese Preposition Selection for Grammatical Error Diagnosis**. COLING 2016.  
Hen-Hsen Huang, Yen-Chi Shao, Hsin-Hsi Chen.[[pdf](https://aclanthology.org/C16-1085/)].

**Neural Network Translation Models for Grammatical Error Correction**. IJCAI 2016.  
S Chollampatt，K Taghipour，HT Ng.[[pdf](https://arxiv.org/pdf/1606.00189.pdf)].

**Exploiting N-Best Hypotheses to Improve an SMT Approach to Grammatical Error Correction**. IJCAI 2016.  
DT Hoang，S Chollampatt，HT Ng.[[pdf](http://www.researchgate.net/publication/303749890_Exploiting_N-Best_Hypotheses_to_Improve_an_SMT_Approach_to_Grammatical_Error_Correction)].

**How Far are We from Fully Automatic High Quality Grammatical Error Correction?**. ACL 2015.  
Christopher Bryant, Hwee Tou Ng.[[pdf](https://aclanthology.org/P15-1068/)].

**Ground Truth for Grammatical Error Correction Metrics**. ACL 2015 short.  
Courtney Napoles, Keisuke Sakaguchi, Matt Post, Joel Tetreault.[[pdf](https://aclanthology.org/P15-2097/)].

**Towards a standard evaluation method for grammatical error detection and correction**. NAACL 2015.  
Mariano Felice, Ted Briscoe.[[pdf](https://aclanthology.org/N15-1060/)].

**Human Evaluation of Grammatical Error Correction Systems**. EMNLP 2015.  
Roman Grundkiewicz, Marcin Junczys-Dowmunt, Edward Gillian.[[pdf](https://aclanthology.org/D15-1052/)].

**Ground Truth for Grammatical Error Correction Metrics**. IJCNLP 2015.  
Courtney Napoles, Keisuke Sakaguchi, Matt Post, Joel Tetreault.[[pdf](https://aclanthology.org/P15-2097/)].

**Go Climb a Dependency Tree and Correct the Grammatical Errors**. EMNLP 2014.  
Longkai Zhang, Houfeng Wang.[[pdf](https://aclanthology.org/D14-1033/)].

**System Combination for Grammatical Error Correction**. EMNLP 2014.  
Raymond Hendy Susanto, Peter Phandi, Hwee Tou Ng.[[pdf](https://aclanthology.org/D14-1102/)].

**Data Driven Grammatical Error Detection in Transcripts of Children’s Speech**. EMNLP 2014.  
Eric Morley, Anna Eva Hallin, Brian Roark.[[pdf](https://aclanthology.org/D14-1106/)].

**Generating artificial errors for grammatical error correction**. EACL 2014.  
Mariano Felice, Zheng Yuan.[[pdf](https://aclanthology.org/E14-3013/)].

**Correcting Grammatical Verb Errors**. EACL 2014.  
Alla Rozovskaya, Dan Roth, Vivek Srikumar.[[pdf](https://aclanthology.org/E14-1038/)].

**Detecting Learner Errors in the Choice of Content Words Using Compositional Distributional Semantics**. COLING 2014.  
Ekaterina Kochmar, Ted Briscoe.[[pdf](https://aclanthology.org/C14-1164/)].

**A Sentence Judgment System for Grammatical Error Detection**. COLING 2014.  
Lung-Hao Lee, Liang-Chih Yu, Kuei-Ching Lee, Yuen-Hsien Tseng, Li-Ping Chang, Hsin-Hsi Chen.[[pdf](https://aclanthology.org/C14-2015/)].

**Automated Grammatical Error Correction for Language Learners**. COLING 2014.  
Joel Tetreault, Claudia Leacock.[[pdf](https://aclanthology.org/C14-3004/)].

**Grammatical Error Correction Using Integer Linear Programming**. ACL 2013.  
Yuanbin Wu, Hwee Tou Ng.[[pdf](https://aclanthology.org/P13-1143/)].

**Joint Learning and Inference for Grammatical Error Correction**. EMNLP 2013.  
Alla Rozovskaya, Dan Roth.[[pdf](https://aclanthology.org/D13-1074/)].

**Automated Grammar Correction Using Hierarchical Phrase-Based Statistical Machine Translation**. IJCNLP 2013.  
Bibek Behera, Pushpak Bhattacharyya.[[pdf](https://aclanthology.org/I13-1122/)].

**Grammatical Error Correction Using Feature Selection and Confidence Tuning**. IJCNLP 2013.  
Yang Xiang, Yaoyun Zhang, Xiaolong Wang, Chongqiang Wei, Wen Zheng, Xiaoqiang Zhou, Yuxiu Hu, Yang Qin.[[pdf](https://aclanthology.org/I13-1148/)].

**A Meta Learning Approach to Grammatical Error Correction**. ACL 2012.  
Hongsuck Seo, Jonghoon Lee, Seokhwan Kim, Kyusong Lee, Sechun Kang, Gary Geunbae Lee.[[pdf](https://aclanthology.org/P12-2064/)].

**Grammar Error Correction Using Pseudo-Error Sentences and Domain Adaptation**. ACL 2012.  
Kenji Imamura, Kuniko Saito, Kugatsu Sadamitsu, Hitoshi Nishikawa.[[pdf]()].

**Better Evaluation for Grammatical Error Correction**. NAACL 2012 short.  
Daniel Dahlmeier, Hwee Tou Ng.[[pdf](https://aclanthology.org/N12-1067/)].

**A Beam-Search Decoder for Grammatical Error Correction**. EMNLP 2012.  
Daniel Dahlmeier, Hwee Tou Ng.[[pdf](https://aclanthology.org/D12-1052/)].

**Problems in Evaluating Grammatical Error Detection Systems**. COLING 2012.  
Martin Chodorow, Markus Dickinson, Ross Israel, Joel Tetreault.[[pdf](https://aclanthology.org/C12-1038/)].

**The Effect of Learner Corpus Size in Grammatical Error Correction of ESL Writings**. COLING 2012.  
Tomoya Mizumoto, Yuta Hayashibe, Mamoru Komachi, Masaaki Nagata, Yuji Matsumoto.[[pdf](https://aclanthology.org/C12-2084/)].

**They Can Help: Using Crowdsourcing to Improve the Evaluation of Grammatical Error Detection Systems**. ACL 2011.  
Nitin Madnani, Martin Chodorow, Joel Tetreault, Alla Rozovskaya.[[pdf](https://aclanthology.org/P11-2089/)].

**Grammatical Error Correction with Alternating Structure Optimization**. ACL 2011.  
Daniel Dahlmeier, Hwee Tou Ng.[[pdf](https://aclanthology.org/P11-1092/)].

**Automated Whole Sentence Grammar Correction Using a Noisy Channel Model**. ACL 2011.  
Y. Albert Park, Roger Levy.[[pdf](https://aclanthology.org/P11-1094/)].

**Grammatical Error Detection for Corrective Feedback Provision in Oral Conversations**. AAAI 2011.  
Sungjin Lee, Hyungjong Noh, Kyusong Lee, Gary Geunbae Lee.[[pdf](https://www.aaai.org/ocs/index.php/AAAI/AAAI11/paper/view/3501/3954)].

**Evaluating performance of grammatical error detection to maximize learning effect**. COLING 2010.  
Ryo Nagata, Kazuhide Nakatani.[[pdf](https://aclanthology.org/C10-2103/)].



## Datasets
### [CTC 2021](https://destwang.github.io/CTC2021-explorer/) :
| dataset | download |
|-|-|
|training data|[download](http://pan.iflytek.com/#/link/0CF7992308445E72001ED08F53266D25) (password: girA)|
|validation data|[download](https://pan.baidu.com/s/1dnpCxGK0m8v-R-wMpYH2kQ) (password: asrb)|

### Others:
| dataset | task | # sents | source | language |
|-|-|-|-|-|
| SIGHAN 2013 | CSC | 350 & 974 | SIGHAN | Zh |
| SIGHAN 2014 | CSC | 6,526 & 526 | SIGHAN | Zh |
| SIGHAN 2015 | CSC | 3,174 & 550 | SIGHAN | Zh |
|[OCR dataset](https://github.com/iqiyi/FASPell)|CSC|4575|[FASPell(iqiyi)](https://www.aclweb.org/anthology/D19-5522.pdf)|Zh|
| [HybridSet](https://github.com/wdimmy/Automatic-Corpus-Generation) | CSC | 270K | - | Zh |
| NLPCC 2018 GEC | GEC | - | NLPCC | Zh |
| CGED | GED | - | HSK | Zh |
| CoNLL 2013 | GEC | 1,381 | CONLL | En |
| CoNLL 2014 | GEC | 1,312 | CONLL | En |
| JFLEG | GEC | 747 | [JFLEG: A Fluency Corpus and Benchmark for Grammatical Error Correction](https://aclanthology.org/E17-2037.pdf) | En |
| NUCLE | GEC | 57k | [Building a Large Annotated Corpus of Learner English: The NUS Corpus of Learner English](https://aclanthology.org/W13-1703.pdf) | En |
| Lang-8 | GEC | 1M+ | Lang-8 | En |
| Write&Improve+LOCNESS  | GEC | 63,683 & 7,632 | - | En |
|MMC+PsyTAR (medica)||512 & 79| - |En|
|brikbeck+holbrook-tagged+holbrook-missp+aspell+wikipedia|(Misspelling word)| 36133/6136 & 1791/1200& 531/450& 2455/1922|[BBK](https://www.dcs.bbk.ac.uk/~ROGER/corpora.htm)|En|
|[TOEFL-Spell](https://github.com/EducationalTestingService/toefl-spell)|-|-|[A Benchmark Corpus of English Misspellings and a Minimally-supervised Model for Spelling Correction](https://www.aclweb.org/anthology/W19-4407.pdf)|En|
|[NUC-GEC](https://www.comp.nus.edu.sg/~nlp/corpora.html)|GEC|500 essays|[How Far are We from Fully Automatic High Quality Grammatical Error Correction?](https://www.aclweb.org/anthology/P15-1068.pdf)|En|
| [BEA2019](https://www.cl.cam.ac.uk/research/nl/bea2019st/) | GEC | 34,308 | BEA | En |
| PIE-synthetic | GEC | 9,000,000 | [Parallel iterative edit models for local sequence transduction](https://aclanthology.org/D19-1435/) | En |
| [clang8](https://github.com/google-research-datasets/clang8) | GEC | 2,372,119 & 114,405 & 44,830 | - | En,GE,RU |
| CTC2021 | CSC | 217,634 | - | Zh |


## Systems & API
Feiying System: http://check.hfl-rc.com/  
Feiying API: https://www.xfyun.cn/services/textCorrection


## Other Resources
### Related Articles
* [语法纠错的研究现状](https://mp.weixin.qq.com/s/0_qp1WsrEsjnj8ST4zQyTQ)
* [文本语法纠错不完全调研](https://mp.weixin.qq.com/s/Dj8KIe6LbVGonV-Kk9mO2Q)

### Shared Task
* [CTC 2021](https://github.com/destwang/CTC2021)
-----
*The above resources are only used for academic research. If there is any infringement of copyright, please contact us to delete it.*
