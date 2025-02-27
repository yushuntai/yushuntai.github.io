---
layout: post
title:  " Gibson法构建ANKRD5过表达载体"
tags: 实验方法与科研小技巧
date:   2022-01-27
categories: Front-end JavaScript
excerpt: 实验方法与科研小技巧
---


**目录：**

* content
{:toc}


## 第一步：通过RNA提取和反转录获得cDNA

### 一、RNA提取


纯化GST-hSpout1-6His
1. 材料
1.1. 提前准备（一份量）
一个	LB板子
15ml	2YT培养基
1L	LB培养基

1.2. 储液配置（1L）
	5M NaCl：584.4g in 1L ddH2O，过滤
	1M Tris-Cl pH7.6：121.14g in 1L ddH2O（HCl与NaOH调pH），过滤
	1M 咪唑（imidazole） pH7.4：68.077g in 1L ddH2O（HCl与NaOH调pH），过滤

1.3. 溶液配置
	1M IPTG：4.766 g IPTG in 10ml ddH2O，过滤后冻存与-20℃，保存一年
	1M DTT：1.54 g DTT in 10ml ddH2O，过滤后冻存与-20℃，保存一年
	6M盐酸胍+12ml乙酸（1L）：先准备200-300ml ddH2O，加入573.18g盐酸胍，加ddH2O，再加乙酸，最后定容
	1M NaOH：40g in 1L ddH2O
	0.5M EDTA（1L）：186.12g in 1L ddH2O，过滤
	0.5M NiSO4（1L）：131.425g 六水合NiSO4 in 1L ddH2O，过滤
	Binding buffer（1L）：
50mM Tris-Cl	50ml 1M Tris-Cl pH7.6
300mM NaCl	60ml 5M NaCl
20 mM咪唑	20ml 1M 咪唑pH7.4
过滤
	Elution buffer（1L）：
50mM Tris-Cl	50ml 1M Tris-Cl pH7.6
300mM NaCl	60ml 5M NaCl
20 mM咪唑	250ml 1M 咪唑pH7.4
过滤
	PBS-DTT（现用现配）：PBS + 200x DTT（1M）
	GST elution pH7.5（现用现配）（10ml）：
50mM Tris-Cl	0.5ml 1M Tris-Cl pH7.6
300mM NaCl	0.6ml 5M NaCl
20mM 还原性谷胱甘肽（GSH，分子量307）	0.06g
HCl与NaOH调pH到7.5

1.4. 其他试剂
	快染液：SDS-PAGE蛋白胶染液，睿博兴科，RB010-500 （灵敏度为100ng） 
	Bradford：Quick Start Bradford 1x Dye Reagent，BIO-RAD，50000205
	Ni柱：ProteinIso® Ni-NTA Resin，全式金，DP101-01
	GST柱：Glutathione Beads 4FF，天地人和，SA010100
2. 方法
第一天
晚上	将冻存菌液划板

第二天（需约6h，在10-12点之间开始实验是比较合适的）
+3h	挑6-8个克隆，接到15ml 2YT培养基（含抗生素）
+2h	将10ml菌液接到1L LB培养基（含抗生素）中
220rpm 37℃，OD600到0.8-1.0
+0.5h	冰浴降温至低于18℃，加入500ul 1M IPTG
+16h	200rpm 18℃ 16h

在收细菌之前先平衡Ni柱与GST柱
	Ni柱重生
如果柱子保存在ddH2O中，
8倍体积binding buffer
如果柱子保存在20%乙醇中，
8倍体积 ddH2O
8倍体积binding buffer
	GST柱重生
如果柱子保存在ddH2O中，
8倍体积PBS-DTT
如果柱子保存在20%乙醇/PBS中，
8倍体积ddH2O
8倍体积 PBS-DTT

第三天（需约14h（Ni柱7h+GST柱7h），9点前开始试验可以做完整个流程（这样最好），若下午开始则只能做完Ni柱，可以将洗脱样品放于4℃，第二天过GST）
+0.5h	4000rpm 30min离心收菌  （此处可以液氮冻存）
+1h	用binding buffer重悬（先加40ml重悬，再用40ml冲洗），超声前混匀
（*留样，样品1-菌液）
55%功率 3s on 7s off 有效时间3min*2（总时间10min*2），中间混匀，补充冰
+1.5h	18000rpm 4℃ 1h离心，用0.45um滤膜过滤上清液，混匀
（*留样，样品2-裂解液）
+1h	样品上柱过两次（不要用针头引流），收集穿出液
（*留样，样品3-Ni穿出）
+0.5h	10倍体积binding buffer洗涤
+0.5h	5倍体积 elution buffer洗脱，注意每流出1ml时，测蛋白浓度
取10μl穿出+10ul快染液，看颜色变化，如果水平低且趋于不变，则停止收样
或用nanodrop测OD280，看吸收曲线，如果水平低且趋于不变，则停止收样
若还有很多样品，则继续洗脱
（*留样，样品4-Ni洗脱）
+2h	若短时间内还会使用
10倍体积ddH2O洗柱，放于4℃
若长时间不用，
10倍体积binding buffer
10倍体积ddH2O洗柱
10倍体积20%乙醇，储存于20%酒精，放于4℃
若柱子纯化一个蛋白使用超过三次或用于纯化另一个蛋白，则需要重生
5倍体积 6M盐酸胍+乙酸
10倍体积 ddH2O
5倍体积0.5M EDTA
10倍体积 ddH2O 
5倍体积 NiSO4
10倍体积ddH2O（若短期保存，则留部分液体直接储存于4℃）
10倍体积20%乙醇（若长期保存，则留部分液体直接储存于4℃）
+2h	将buffer置换为PBS-DTT，超滤管4000rpm 4℃离心
+2h	与重生好的GST beads 4℃旋转孵育2h
+0.5h	上柱，收穿出
（*留样，样品5-GST穿出）
+0.5h	10倍体积PBS-DTT洗涤
+0.5h	用2倍体积GST elution buffer洗脱，
混匀后收样
（*留样，样品6-GST洗脱）
跑胶，快染液10min-2h，后用水洗
+1.5h	浓缩到1mg/ml
同时重生GST柱子
10倍体积ddH2O洗柱
5倍体积 6M盐酸胍
10倍体积 ddH2O（若短期保存，则留部分液体直接储存于4℃）
10倍体积20%乙醇/PBS（若长期保存，则留部分液体直接储存于4℃）















1) 2个1.5ml 的 Rnase free 的EP管，各加500µL的TRIZOL。

2) 钻头清洁干净，置于其中一个EP管里的TRIZOL泡着。

3) 取小鼠一侧testis置于另一管TRIZOL中，用钻头充分打成匀浆，RT静置 5min。

4) 100µL氯仿（ TRIZOL 的1/5体积），剧烈混匀15s， RT静置 3min，4℃ 12000X g 15min离心。

5) 重复上步骤2-3次。

6) 配1%胶。

7) 250µL异丙醇（ TRIZOL 的1/2体积），轻柔颠倒20下，RT静置 10min，4℃ 12000X g 10min离心，弃液相。

8) 加500µL （ TRIZOL 的1/1体积） 的75%酒精，摇匀，vortex， 4℃ 7500X g 5min离心。

9) 弃上清，吸干液体，3-5min晾干。

10)  加20µL水震荡混匀，65℃ 3min，立即置于冰上。

11)  测RNA浓度，取2µ跑胶（1%胶 140V 15min），28s：18s=2:1，使用marker III 2000/1200/200各有一条带。（哺乳动物的RNA包括**mRNA**，**rRNA**，**tRNA**和**小RNA**，根据分子量和沉降系数的不同，**rRNA**又可分为**28s, 18s**和**5s rRNA**。从**RNA**的含量上看，**rRNA**是几种RNA中最多的，高达**90%**以上，而**mRNA**很少，只有**1-2%**，而其他两种**RNA**的分子量比较小，所以凝胶电泳的结果上只能看到三条带。而这**三条带的完整性，就代表了mRNA的完整性**，若三条带成弥散状，说明提取的RNA不太好。）

### 二、反转录

#### 1) 去除基因组DNA：

|成分|加量|
|:---:|:---:|
|5X gDNA clean Reaction Mix|2µL|
|Total RNA|1µg左右|
|RNase free water|up to 10µL|

 反应条件： 42℃   2min   4℃   ∞ 

#### 2) 反转录反应：
 
|成分|加量|
|:---:|:---:|
|步骤2）反应液|10 µL|
|5X Evo M-MLV RT Reaction Mix|4 µL|
|RNase free water|6 µL|
 
反应条件：**37℃   15 min   85℃   5 sec   4℃   ∞**

反转录所得cDNA可以冻存在-20℃冰箱，提取的RNA可东存在-80℃冰箱。



## 第二步：酶切载体产生质粒骨架

[![7XL8aV.png](https://s4.ax1x.com/2022/01/27/7XL8aV.png)](https://imgtu.com/i/7XL8aV)



1） 质粒用Hind III 和 AgeI进行酶切。

**具体步骤：**

|成分|加量|
|:---:|:---:|
|Plasmid|1 µg|
|Hind III|1 µL|
|Age I|1 µL|
|Cutsmart |4 µL|
|H2O| 补足40 µL|





酶切条件：**37℃ 3h 酶切质粒**

1% 胶回收酶切产物（有 3000 和 4000 两个片段，回收4000的）

## 第三步：下载ANKRD5蛋白编码序列

[![7XOUFf.png](https://s4.ax1x.com/2022/01/27/7XOUFf.png)](https://imgtu.com/i/7XOUFf)

[ANKRD5蛋白编码序列](https://www.ncbi.nlm.nih.gov/nuccore/NM_175667.4)

[查找基因序列和CDS序列的方法](http://www.360doc.com/content/18/0428/15/48272598_749455980.shtml)  


## 第四步：引物设计和分段PCR

通过对引物进行设计使cDNA两端带上载体骨架同源臂（分两次P）。

[![7XXQA0.png](https://s4.ax1x.com/2022/01/27/7XXQA0.png)](https://imgtu.com/i/7XXQA0)


[![7XjhL9.png](https://s4.ax1x.com/2022/01/27/7XjhL9.png)](https://imgtu.com/i/7XjhL9)

目的产物2400bp左右，尽量用**Q5**体系，该体系保真度更高。下面为两种PCR体系的配比：



**Q5 PCR 体系：**

|成分|加量|
|:---:|:---:|
|Q5酶|12.5 µL(预分装的)  速度：1min 2k|
|cDNA|0.5 µL|
|F|0.6 µL|
|R|0.6 µL|
|H2O|10.8 µL|

 总体系 25 µl，PCR仪器有现成的PCR程序可用，P两管做胶回收。



**Primer STAR PCR 体系：**

|成分|加量|
|:---:|:---:|
|5x buffer|10 µL|
|dNTP|4 µL|
|cDNA|1 µL|
|F|0.5 µL|
|R|0.5 µL|
|酶|0.5 µL|
|H2O|33.5 µL|

 总体系 25 µl，PCR仪器有现成的PCR程序可用，P两管做胶回收。

每管还可以加入0.2~0.3微升的DMSO，DMSO利于减少DNA的二级结构，使G、C含量高的模板易于完全变性，从而提高PCR特异性，帮助扩增一些难扩的模板。但要摸索，量大的话会抑制扩增，而且最好用于扩增1KB以上模板。

[![7XzmGV.png](https://s4.ax1x.com/2022/01/27/7XzmGV.png)](https://imgtu.com/i/7XzmGV)

## 第五步：Gibson连接

**Gibson连接体系：**

|成分|加量|
|:---:|:---:|
|Gibson酶|5 µL(预分装的，-20℃保存)|
|带载体骨架同源臂的cDNA|？ µL|
|载体骨架|？ µL|

Vector 和目的片段 **1:3** 的摩尔比进行配比（有一个ligation Calculator的excel文件可以进行计算），**50℃ 50min**的条件进行连接。



### 1）连接产物转化感受态

5 µL连接产物转化感受态（用的博迈德的Trans10感受态）。

1）50 µL感受态冰上化冻，加入5 µL gibson连接产物，手指弹动离心管，混匀感受态和连接产物，冰上静置30 min。

2) 42℃热激 90sec。

3) 冰上静置2min。

4) 加入200 µL的无抗LB，37℃ 摇床上180 转 30min。

5) 取50 µL涂抗性板（该载体为kana抗性），13h后挑单克隆。

6）每个单克隆加500 µL抗性LB，37℃ 摇床上240 转 1-2h。

7）然后每个克隆摇起来的菌液抽取1微升进行菌液PCR。

### 2）菌液PCR克隆鉴定

**菌液 PCR体系：**

|成分|加量|
|:---:|:---:|
|10X buffer|2 µL|
|dNTP|1.5 µL|
|F|0.3 µL|
|R|0.3 µL|
|Tag酶|0.3 µL|
|H2O| 14.9 µL|

[![7jSTne.png](https://s4.ax1x.com/2022/01/27/7jSTne.png)](https://imgtu.com/i/7jSTne)

**菌液PCR结果如下：**

[![7jSzjS.png](https://s4.ax1x.com/2022/01/27/7jSzjS.png)](https://imgtu.com/i/7jSzjS)


确定PCR产物大小是否对应。然后挑选几个菌液PCR结果正确的进行送测序。

## 第六步：测序鉴定载体是否构建成功

|姓名|性别|语文成绩|数学成绩|英语成绩|思想品德成绩|
|:---:|:---:|:---:|:---:|:---:|:---:|
|宋江|男|90|61|88|2|
|鲁智深|男|83|96|40|98|
|武松|男|80|80|80|78|
|卢俊义|男|90|96|70|60|
|李逵|男|0|3|0|0|9|
|扈三娘|女|79|66|76|40|

