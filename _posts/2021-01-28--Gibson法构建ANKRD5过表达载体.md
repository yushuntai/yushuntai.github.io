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

