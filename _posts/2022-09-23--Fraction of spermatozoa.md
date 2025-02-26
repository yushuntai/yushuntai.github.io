---
layout: post
title:  " Fraction of spermatozoa"
tags: 实验方法与科研小技巧
date:   2022-09-23
categories: Front-end JavaScript
excerpt: 实验方法与科研小技巧
---


**目录：**

* content
{:toc}

## 溶液配方

**1% Triton X-100 PH=7.5**

| 成分|50mL体系加量   |
| :----: | :------: |
| 50mM NaCl |  0.1461g |
| 20mM Tris-HCl |  1mL 1M的母液 |
| Triton X-100 |  500uL |

调节PH

**1% SDS PH=6.0**

| 成分|50mL体系加量   |
| :----: | :------: |
| 75mM NaCl |  0.21915g |
| 24mM EDTA |  2.4mL 0.5M的母液 |
| 1% SDS |  0.5g |

调节PH

**Sample buffer**

| 成分|50mL体系加量   |
| :----: | :------: |
| 66mM Tris-HCl |  3.3mL 1M母液 |
| 2% SDS |  1g |
| 10% 甘油 |  5mL |
| 0.005溴酚蓝 |  2.5mg |

调节PH

**0.5M EDTA PH=8.0配方（100mL总体系）：**<br>
14.612g EDTA + 6.7g NaOH片，先加85mLddH2O溶，因为6.7g左右NaOH片可使体积增加10mL左右，然后再调PH值。

## 实验步骤
1）一只WT鼠和一只ANKRD5-cFLAG鼠，两侧epi cauda，置于500uL 37℃预热的PBS中，释放精子1h；<br>
2）弃组织，4℃ 1500g 10min离心，500uL PBS重悬，洗一遍；<br>
3）100uL 1% Triton X-100裂解液重悬精子，4℃ 2h；<br>
4）4℃ 1500g 10min离心，取上清为Triton-soluble fraction；<br>
5）沉淀用200uL的1% Triton X-100裂解液洗两遍；<br>
6）1% SDS裂解液重悬精子，室温 1h 每15min涡旋震荡一下；<br>
7）室温1500g 10min离心，取上清为SDS-soluble fraction；<br>
8）沉淀用200uL 1% SDS裂解液洗两遍；<br>
9）100uL Sample buffer裂解液重悬，100℃煮10min，取上清为SDS-resistant fraction；<br>

从左到右上样孔分别为：Marker(3uL)、WT-Triton-soluble(20uL)、WT-SDS-soluble(20uL)、WT-SDS-resistant(20uL)、A5-cFLAG-Triton-soluble(20uL)、A5-cFLAG-SDS-soluble(20uL)、A5-cFLAG-SDS-resistant(20uL)、Marker(10uL)<br>
还有一个膜是各上样50uL，FLAG比较清晰，而AcetTUB过曝严重。


anti-FLAG(M2) 1:5000<br>
anti-AcetTUB sigma T7451 1:1000<br>
一抗：4℃过夜<br>
二抗：1:5000 室温1.5h<br>
中间TBST每10min洗一次，共3次<br>
5%脱脂奶粉封的有点久，估计有两三个小时。<br>

