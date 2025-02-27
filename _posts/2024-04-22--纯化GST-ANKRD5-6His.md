---
layout: post
title:  " 纯化GST-ANKRD5-6His"
tags: 实验方法与科研小技巧
date:   2024-04-22
categories: Front-end JavaScript
excerpt: 实验方法与科研小技巧
---


**目录：**

* content
{:toc}

# BACKGROUND
## 表达系统介绍
[总概篇：真核表达系统（第一弹）——酵母表达系统](https://mp.weixin.qq.com/s?__biz=Mzg4Nzc1MDYyOQ==&mid=2247485104&idx=1&sn=d2c26bd6dfaa766dda0eb9d93a55948e&chksm=cf84ec3af8f3652c503be8164f422309e1b85b123bf9f5df522b592f0b929f41ca41af5c4c52&scene=21#wechat_redirect)
<br>
[真核表达系统第二弹（上）—哺乳动物细胞表达系统](https://mp.weixin.qq.com/s?__biz=Mzg4Nzc1MDYyOQ==&mid=2247485173&idx=1&sn=1e7e93509754f88292ca9e46f6ee6f49&chksm=cf84ec7ff8f365695fbd1f2ec34cf81bb65ad4d6a892e66ec632f38a29a96fa7f7d65f92153a&scene=21#wechat_redirect)
<br>
[真核表达系统第二弹（下）——哺乳动物细胞表达系统](https://mp.weixin.qq.com/s?__biz=Mzg4Nzc1MDYyOQ==&mid=2247485183&idx=1&sn=cdd6b00144d89c4ca4488e1ca16b9ef5&chksm=cf84ec75f8f365639205f9a6c9c2d28a7cb4113ed079ec54c23965e9fe54403cbadaa24f20d0&scene=21#wechat_redirect)
<br>
[真核表达系统（第三弹）—昆虫杆状病毒表达系统](https://mp.weixin.qq.com/s/mC6hXcGTd4j-GiWi7Ai3AA)
<br>
## 蛋白表达需要用表达型菌株感受态。
启动子需要与 RNA聚合酶结合启动DNA转录。质粒的T7启动子需要T7 RNA聚合酶才能发挥功能。感受态BL21、BL21(DE3)及BL21(DE3) pLysS不一样。<br>
**BL21**没有T7 RNAP (RNA polymerase)基因，因此不能表达T7promoter驱动的目的基因(如：pET系列)，BL21含有大肠杆菌RNAP，适合依赖于大肠杆菌RNAP的原核系统的表达(如：pGEX，pMAL质粒)。也可以表达大肠杆菌启动子lac、tac、tre 及trp控制的基因。<br>
**BL21(DE3)**：该菌株为BL21菌株染色体整合了λ噬菌DE3区，该区含有T7 RNAP基因及其启动子lacUV5，可以表达出T7 RNAP；lacUV5启动子受到lacI抑制，而加入IPTG可解除抑制，即诱导表达T7 RNAP，进而表达T7 promoter控制的目的基因。原核表达质粒上有些会有lacI编码基因。但是包括lacI在内的抑制蛋白都不是绝对抑制的，即存在泄漏表达。BL21(DE3)菌株缺少Lon蛋白酶、OmpT蛋白酶，可以减少对重组蛋白的降解，有利于外源蛋白的纯化。有背景表达， 故该菌株适合用于非毒性蛋白的表达，不适用于毒性蛋白的表达。<br>
**BL21(DE3)pLysS**：含有pLysS质粒，一种与pET共存的表达T7裂解酶的质粒，可以减少目的基因的本底表达，提供更严紧的控制。<br>

## IPTG诱导蛋白表达的原理

**一言以蔽之，基因表达需要操纵基因，而Lac阻遏物会抑制操纵基因，IPTG可以与Lac阻遏物结合从而解除对操纵基因的抑制，使基因表达。**

原核生物绝大多数基因按功能相关性成簇排列，且密集于染色体上，共同形成一个转录单位——操纵子（元），也称基因表达的协同单位(a coordinated unit of gene expression)。E.coli的乳糖操纵子（元）含Z、Y及A三个结构基因，分别编码β-半乳糖苷酶（β-galactosidase）、通透酶（permease）和乙酰基转移酶（transacetylase)；此外还有调控基因：操纵序列O（operator）、启动序列P（promoter）；而I(编码Lac阻遏物，Lac repressor)不属于乳糖操纵子。<br>
没有乳糖存在时，Lac阻遏物与操纵基因O结合，阻碍RNA聚合酶与P序列结合，抑制转录启动。<br>
当有诱导剂与Lac阻遏物结合使其蛋白构象发生变化，致阻遏物从操纵基因O上解离下来，RNA聚合酶不再受阻碍，转录启动。<br>
操纵子体系中，真正的诱导剂是乳糖被β-半乳糖苷酶催化的产物(半乳糖）。IPTG为半乳糖类似物作为诱导剂，IPTG为乳糖类似物，是极强的诱导剂，不被细菌代谢，十分稳定。IPTG对人体具有潜在毒性，当用于诱导表达应用于人体的重组药物时，有可能对最终的产品带来不利影响。乳糖是一种二糖，无毒性，且价格远低于IPTG，其有可能成为IPTG诱导剂，且可被菌体代谢利用，与IPTG不同，乳糖自身无法进入到菌体内部，需借助乳糖透过酶的作用，乳糖进入细胞后仍不能诱导Lac 启动子的启动。需经过β-半乳糖苷酶转化为异乳糖才会起到诱导剂的作用。与IPTG相比，利用乳糖作为诱导剂其诱导过程更为复杂和麻烦，而且诱导效果也远不及IPTG。<br>

<img src="https://github.com/yushuntai/yushuntai.github.io/assets/61654690/0a1bf54f-3758-4eb3-ae42-436f95a5a8c4" width="666">

## Ni柱纯化蛋白原理
Ni柱中的氯化镍或者硫酸镍可以与有His(组蛋白)标签的碱性蛋白或者咪唑结合.Ni-NTA纯化介质是把螯合剂NTA共价偶联到琼脂糖介质上，然后再螯合Ni2+制备而成。NTA能够通过四个位点牢固的螯合Ni2+从而减少纯化过程中Ni2+泄露到蛋白样品中。Ni-NTA纯化介质可以纯化任何表达系统(原核，酵母，昆虫细胞和哺乳动物细胞等表达系统)表达的天然或变性的His-标签蛋白。结合在介质上的蛋白可以通过低pH缓冲液、咪唑溶液甚至组氨酸溶液洗脱下来。

Ni为**金属螯合亲和层析**又称为**固定金属离子亲和色谱**（immobilized metal ion affinity chromatography，IMAC），1975年由Porath等发明。其纯化原理是利用蛋白质表面的组氨酸与多种过渡金属离子如Cu2+，Zn2+，Ni2+，Fe3+ 形成配位相互作用，从而吸附富含这类氨基酸的蛋白质，达到分离纯化的目的。因此，固定有这些金属离子的琼脂糖凝胶就能够选择性地纯化这类含有多个组氨酸的蛋白以及多肽和核苷酸。半胱氨酸和色氨酸与固定金属离子结合力要远小于组氨酸残基，对纯化影响不大。镍离子金属螯合亲和层析的螯合配基有**IDA、NTA、TED**等.镍离子有六个螯合价位,Ni-IDA螯合了三价,剩余三价;Ni-NTA螯合了四价,剩余两价;Ni-TED螯合了五价,剩余一价;即能与His tag结合的位点还剩3，2，1个。所以IDA与His tag结合力最强，特异性最弱，而TED则相反。我们在实际应用中常选择载量与特异性适中的NTA类型。

<img src="https://github.com/yushuntai/yushuntai.github.io/assets/61654690/d32f4a62-1e5d-4ad7-a278-a5040808255e" width="666">

在Ni柱的使用中，应当避免缓冲液中存在还原剂和螯合剂，以免Ni2+被还原而脱落。如果柱料使用太久积累了很多杂蛋白，可用EDTA将Ni2+螯合下来，再用NaOH清洗柱料后，重新螯合Ni离子，即可完成再生。平时不用时，应保存在20%乙醇中防止长菌。

Ni柱的洗脱通常采用竞争洗脱，先用低浓度的咪唑将杂蛋白和结合不牢的蛋白洗去，再用合适的浓度将目的蛋白洗脱。洗脱的先后顺序与蛋白的结合能力相关。


## GST柱纯化蛋白原理
GST tag是一种常用的蛋白纯化标签，它利用谷胱甘肽转移酶（GST）与谷胱甘肽（glutathione）之间的高亲和力来纯化目标蛋白。通过亲和层析，使用谷胱甘肽琼脂糖珠（如Glutathione Sepharose）或磁珠等含有谷胱甘肽结合物的柱子，将裂解的细胞提取物加载到柱子中。由于GST与谷胱甘肽的高亲和力，GST-目标蛋白融合蛋白会与柱子上的谷胱甘肽结合物结合。谷胱甘肽作为固相材料，能够选择性地捕获含有GST标签的融合蛋白，而非融合蛋白等其他细胞组分。通过洗脱和解离步骤，目标蛋白可以从柱子上被分离和纯化出来。




# 载体信息
```
ACGTTATCGACTGCACGGTGCACCAATGCTTCTGGCGTCAGGCAGCCATCGGAAGCTGTGGTATGGCTGTGCAGGTCGTAAATCACTGCATAATTCGTGTCGCTCAAGGCGCACTCCCGTTCTGGATAATGTTTTTTGCGCCGACATCATAACGGTTCTGGCAAATATTCTGAAATGAGCTGTTGACAATTAATCATCGGCTCGTATAATGTGTGGAATTGTGAGCGGATAACAATTTCACACAGGAAACAGTATTCATGTCCCCTATACTAGGTTATTGGAAAATTAAGGGCCTTGTGCAACCCACTCGACTTCTTTTGGAATATCTTGAAGAAAAATATGAAGAGCATTTGTATGAGCGCGATGAAGGTGATAAATGGCGAAACAAAAAGTTTGAATTGGGTTTGGAGTTTCCCAATCTTCCTTATTATATTGATGGTGATGTTAAATTAACACAGTCTATGGCCATCATACGTTATATAGCTGACAAGCACAACATGTTGGGTGGTTGTCCAAAAGAGCGTGCAGAGATTTCAATGCTTGAAGGAGCGGTTTTGGATATTAGATACGGTGTTTCGAGAATTGCATATAGTAAAGACTTTGAAACTCTCAAAGTTGATTTTCTTAGCAAGCTACCTGAAATGCTGAAAATGTTCGAAGATCGTTTATGTCATAAAACATATTTAAATGGTGATCATGTAACCCATCCTGACTTCATGTTGTATGACGCTCTTGATGTTGTTTTATACATGGACCCAATGTGCCTGGATGCGTTCCCAAAATTAGTTTGTTTTAAAAAACGTATTGAAGCTATCCCACAAATTGATAAGTACTTGAAATCCAGCAAGTATATAGCATGGCCTTTGCAGGGCTGGCAAGCCACGTTTGGTGGTGGCGACCATCCTCCAAAATCGGATCTGGAAGTTCTGTTCCAGGGGCCCCTGGGATCCCCGgAATTCCCGGGTCGACATatggctttggcagacaagagacttgagaacttacagatctacagagttcttcagtgtgttcgcaacaaagacaagaagcagatagaaaagctgaccaggcttgggtaccctgagctaatcaacttcaccgaacccatagatgggctgagtgctctccacttagcctccatttccaacgacactgacatggtcagcttcctcctcaaacttggtgcgcatcctgatgtgcaagaccacatgggctgtaccccgaccatgagagctgccgagctgggccatgagttgtcaatggaaattttagccaaggccaaagctgatatgacaatagttgataatgaaggaaaaggtgttctgttttactgcatcctgcccactaagcggcactatcgatgctcactgattgccttggagcatggtgcagatgtcaacaatatcacctatgaagggaagccagtgttcctcagagcttgcgaggaagcacatgatgtgaaggatatgtgcctgacatttttggagaaaggagccaatcctaatgctatcaacacatccacaggacgcacggctttgatggaatcgtcaagagaaggggtgctggaaatagttcgtggcatattggaaagaggaggtgaagtgaacgcatatgacaatgatagacaccacgctgctcattttgctgccaaaggaggcttttttgatattctgaagctcctctttgcctacaatggagacatggggttaattggaatggatgggaacacaccacttcactttgctgccatggggggttttgcagattgctgtaaatatatagctcagcgaggatgtgacctgaaatggaaaaatttggaacataaaacaccccgagttgtggcgaaagacggaggctttaaagctgctagcaaggaaatacgtcgagcagagcggactgccgctaaactcgctaagacaggagcaaaaaatcctaaccctctctgggccctcaggctgcatgactggtccatagagcacgagacttcccttcggaacgcctttaagttcgtggacaggggcgatggcgtagtcagcaaagatgacttcgtggtggccctggaggagaggcaagagtatgccacctcagagcagttgctttccgttgctcaaatgcacgaaaaaagtcgaggaggcggggtcaacattaatgagttctttaagggaaccaaatatttaagcaagtcgtacgtattgggatctttcgggcctaagaaaaagaaaagggggttgggcaaaaagccaaggaaaggcaagtttgttttgcctctccccatctgcaccatcccggagaacgccttcccgcggcggccagatgggggcccgccctactacatgattgagacctaccagaatgtctccgacagccacaggttcaaccgggaccacccgcccgagcacccaatccaggatgattccgagtggtacatcgatgatccgagtagggtcttcgcaaatattagttttatcaccaaagcaggagatctggcctctctgaaaaaggccatcgaaacaggaatacccgtggatatgaaggacaatacttacaagactcctctcatgatagcgtgtgccagtggcaacattgatgtggtcaagtttcttatcgaaaagggggcaaatgttaatgcaacagataattttctatggactccacttcattttgcatgccatgctggccagcaagacattgttgagcttcttgttaaagctggagcttcaatagatgcaacatcaatcaacaactccactccgttaagcagagccattgaaagctgtaggctggacactgtaaaatacctacttgatatgggtgccaaattccagattgaaaacagaaaaggacatgctgccatggatattgcaaaggcatatgctgattatagaataattgatatgataaaagaaaagctagataacctgcctaaacaagcagataatcagaaaatgaaaggcaagcttcctaaactgaagacagaaggcacggatgttaagaaagaagaggaaacactgtcatccatttacactgtgccagcaataacagaggagaagaaagtccacagggatagtgtggtttacctcaattccctgattaccagtggcttcaccaagaaagttgatatcacatttatccccaaaaggatttggagtcctgaagccacaacagcagagctgatcaggaagagggagctccggagggagaggttcacatacgaggtggactttgaagacttcatgatgcctttccaaaagaacatcacggagaaagctcaggcactggaggcaacactcaagaacGGAGGCGGTAGCcatcaccatcatcaccacTGAGCGGCCGCATCGTGACTGACTGACGATCTGCCTCGCGCGTTTCGGTGATGACGGTGAAAACCTCTGACACATGCAGCTCCCGGAGACGGTCACAGCTTGTCTGTAAGCGGATGCCGGGAGCAGACAAGCCCGTCAGGGCGCGTCAGCGGGTGTTGGCGGGTGTCGGGGCGCAGCCATGACCCAGTCACGTAGCGATAGCGGAGTGTATAATTCTTGAAGACGAAAGGGCCTCGTGATACGCCTATTTTTATAGGTTAATGTCATGATAATAATGGTTTCTTAGACGTCAGGTGGCACTTTTCGGGGAAATGTGCGCGGAACCCCTATTTGTTTATTTTTCTAAATACATTCAAATATGTATCCGCTCATGAGACAATAACCCTGATAAATGCTTCAATAATATTGAAAAAGGAAGAGTATGAGTATTCAACATTTCCGTGTCGCCCTTATTCCCTTTTTTGCGGCATTTTGCCTTCCTGTTTTTGCTCACCCAGAAACGCTGGTGAAAGTAAAAGATGCTGAAGATCAGTTGGGTGCACGAGTGGGTTACATCGAACTGGATCTCAACAGCGGTAAGATCCTTGAGAGTTTTCGCCCCGAAGAACGTTTTCCAATGATGAGCACTTTTAAAGTTCTGCTATGTGGCGCGGTATTATCCCGTGTTGACGCCGGGCAAGAGCAACTCGGTCGCCGCATACACTATTCTCAGAATGACTTGGTTGAGTACTCACCAGTCACAGAAAAGCATCTTACGGATGGCATGACAGTAAGAGAATTATGCAGTGCTGCCATAACCATGAGTGATAACACTGCGGCCAACTTACTTCTGACAACGATCGGAGGACCGAAGGAGCTAACCGCTTTTTTGCACAACATGGGGGATCATGTAACTCGCCTTGATCGTTGGGAACCGGAGCTGAATGAAGCCATACCAAACGACGAGCGTGACACCACGATGCCTGCAGCAATGGCAACAACGTTGCGCAAACTATTAACTGGCGAACTACTTACTCTAGCTTCCCGGCAACAATTAATAGACTGGATGGAGGCGGATAAAGTTGCAGGACCACTTCTGCGCTCGGCCCTTCCGGCTGGCTGGTTTATTGCTGATAAATCTGGAGCCGGTGAGCGTGGGTCTCGCGGTATCATTGCAGCACTGGGGCCAGATGGTAAGCCCTCCCGTATCGTAGTTATCTACACGACGGGGAGTCAGGCAACTATGGATGAACGAAATAGACAGATCGCTGAGATAGGTGCCTCACTGATTAAGCATTGGTAACTGTCAGACCAAGTTTACTCATATATACTTTAGATTGATTTAAAACTTCATTTTTAATTTAAAAGGATCTAGGTGAAGATCCTTTTTGATAATCTCATGACCAAAATCCCTTAACGTGAGTTTTCGTTCCACTGAGCGTCAGACCCCGTAGAAAAGATCAAAGGATCTTCTTGAGATCCTTTTTTTCTGCGCGTAATCTGCTGCTTGCAAACAAAAAAACCACCGCTACCAGCGGTGGTTTGTTTGCCGGATCAAGAGCTACCAACTCTTTTTCCGAAGGTAACTGGCTTCAGCAGAGCGCAGATACCAAATACTGTCCTTCTAGTGTAGCCGTAGTTAGGCCACCACTTCAAGAACTCTGTAGCACCGCCTACATACCTCGCTCTGCTAATCCTGTTACCAGTGGCTGCTGCCAGTGGCGATAAGTCGTGTCTTACCGGGTTGGACTCAAGACGATAGTTACCGGATAAGGCGCAGCGGTCGGGCTGAACGGGGGGTTCGTGCACACAGCCCAGCTTGGAGCGAACGACCTACACCGAACTGAGATACCTACAGCGTGAGCTATGAGAAAGCGCCACGCTTCCCGAAGGGAGAAAGGCGGACAGGTATCCGGTAAGCGGCAGGGTCGGAACAGGAGAGCGCACGAGGGAGCTTCCAGGGGGAAACGCCTGGTATCTTTATAGTCCTGTCGGGTTTCGCCACCTCTGACTTGAGCGTCGATTTTTGTGATGCTCGTCAGGGGGGCGGAGCCTATGGAAAAACGCCAGCAACGCGGCCTTTTTACGGTTCCTGGCCTTTTGCTGGCCTTTTGCTCACATGTTCTTTCCTGCGTTATCCCCTGATTCTGTGGATAACCGTATTACCGCCTTTGAGTGAGCTGATACCGCTCGCCGCAGCCGAACGACCGAGCGCAGCGAGTCAGTGAGCGAGGAAGCGGAAGAGCGCCTGATGCGGTATTTTCTCCTTACGCATCTGTGCGGTATTTCACACCGCATAAATTCCGACACCATCGAATGGTGCAAAACCTTTCGCGGTATGGCATGATAGCGCCCGGAAGAGAGTCAATTCAGGGTGGTGAATGTGAAACCAGTAACGTTATACGATGTCGCAGAGTATGCCGGTGTCTCTTATCAGACCGTTTCCCGCGTGGTGAACCAGGCCAGCCACGTTTCTGCGAAAACGCGGGAAAAAGTGGAAGCGGCGATGGCGGAGCTGAATTACATTCCCAACCGCGTGGCACAACAACTGGCGGGCAAACAGTCGTTGCTGATTGGCGTTGCCACCTCCAGTCTGGCCCTGCACGCGCCGTCGCAAATTGTCGCGGCGATTAAATCTCGCGCCGATCAACTGGGTGCCAGCGTGGTGGTGTCGATGGTAGAACGAAGCGGCGTCGAAGCCTGTAAAGCGGCGGTGCACAATCTTCTCGCGCAACGCGTCAGTGGGCTGATCATTAACTATCCGCTGGATGACCAGGATGCCATTGCTGTGGAAGCTGCCTGCACTAATGTTCCGGCGTTATTTCTTGATGTCTCTGACCAGACACCCATCAACAGTATTATTTTCTCCCATGAAGACGGTACGCGACTGGGCGTGGAGCATCTGGTCGCATTGGGTCACCAGCAAATCGCGCTGTTAGCGGGCCCATTAAGTTCTGTCTCGGCGCGTCTGCGTCTGGCTGGCTGGCATAAATATCTCACTCGCAATCAAATTCAGCCGATAGCGGAACGGGAAGGCGACTGGAGTGCCATGTCCGGTTTTCAACAAACCATGCAAATGCTGAATGAGGGCATCGTTCCCACTGCGATGCTGGTTGCCAACGATCAGATGGCGCTGGGCGCAATGCGCGCCATTACCGAGTCCGGGCTGCGCGTTGGTGCGGATATCTCGGTAGTGGGATACGACGATACCGAAGACAGCTCATGTTATATCCCGCCGTCAACCACCATCAAACAGGATTTTCGCCTGCTGGGGCAAACCAGCGTGGACCGCTTGCTGCAACTCTCTCAGGGCCAGGCGGTGAAGGGCAATCAGCTGTTGCCCGTCTCACTGGTGAAAAGAAAAACCACCCTGGCGCCCAATACGCAAACCGCCTCTCCCCGCGCGTTGGCCGATTCATTAATGCAGCTGGCACGACAGGTTTCCCGACTGGAAAGCGGGCAGTGAGCGCAACGCAATTAATGTGAGTTAGCTCACTCATTAGGCACCCCAGGCTTTACACTTTATGCTTCCGGCTCGTATGTTGTGTGGAATTGTGAGCGGATAACAATTTCACACAGGAAACAGCTATGACCATGATTACGGATTCACTGGCCGTCGTTTTACAACGTCGTGACTGGGAAAACCCTGGCGTTACCCAACTTAATCGCCTTGCAGCACATCCCCCTTTCGCCAGCTGGCGTAATAGCGAAGAGGCCCGCACCGATCGCCCTTCCCAACAGTTGCGCAGCCTGAATGGCGAATGGCGCTTTGCCTGGTTTCCGGCACCAGAAGCGGTGCCGGAAAGCTGGCTGGAGTGCGATCTTCCTGAGGCCGATACTGTCGTCGTCCCCTCAAACTGGCAGATGCACGGTTACGATGCGCCCATCTACACCAACGTAACCTATCCCATTACGGTCAATCCGCCGTTTGTTCCCACGGAGAATCCGACGGGTTGTTACTCGCTCACATTTAATGTTGATGAAAGCTGGCTACAGGAAGGCCAGACGCGAATTATTTTTGATGGCGTTGGAATT

```

# 材料准备
**Amp+ 抗性固体LB板子**：<br>
**1L LB液体培养基**：？？？<br>
**5M NaCl：** 584.4g in 1L ddH2O，过滤<br>
**1M Tris-Cl** pH7.6：121.14g in 1L ddH2O（HCl与NaOH调pH），过滤<br>
**1M 咪唑（imidazole）** pH7.4：68.077g in 1L ddH2O（HCl与NaOH调pH），过滤<br>
**1M IPTG**：4.766 g IPTG in 10ml ddH2O，过滤后冻存与-20℃，保存一年<br>
**1M DTT**：1.54 g DTT in 10ml ddH2O，过滤后冻存与-20℃，保存一年<br>
**6M盐酸胍+12ml乙酸（1L）**：先准备200-300ml ddH2O，加入573.18g盐酸胍，加ddH2O，再加乙酸，最后定容<br>
**1M NaOH**：40g in 1L ddH2O<br>
**0.5M EDTA（1L）**：186.12g in 1L ddH2O，过滤<br>
**0.5M NiSO4（1L）**：131.425g 六水合NiSO4 in 1L ddH2O，过滤<br>

**Binding buffer（1L）**：
	
|成分|加量|
|:---:|:---:|
|50mM Tris-Cl|50ml 1M Tris-Cl pH7.6|
|300mM NaCl|60ml 5M NaCl|
|20 mM咪唑|20ml 1M 咪唑pH7.4|

过滤

**Elution buffer（1L）**：

|成分|加量|
|:---:|:---:|
|50mM Tris-Cl|50ml 1M Tris-Cl pH7.6|
|300mM NaCl|60ml 5M NaCl|
|250 mM咪唑|250ml 1M 咪唑pH7.4|

过滤

**PBS-DTT（现用现配）**：PBS + 200x DTT（1M）
**GST elution pH7.5（现用现配）（10ml）**：

|成分|加量|
|:---:|:---:|
|50mM Tris-Cl|0.50ml 1M Tris-Cl pH7.6|
|300mM NaCl|0.6ml 5M NaCl|
|20mM 还原性谷胱甘肽（GSH，分子量307）mM咪唑|0.06g|

HCl与NaOH调pH到7.5

**快染液**：SDS-PAGE蛋白胶染液，睿博兴科，RB010-500 （灵敏度为100ng） <br>
**Bradford**：Quick Start Bradford 1x Dye Reagent，BIO-RAD，50000205<br>
**Ni柱**：ProteinIso® Ni-NTA Resin，全式金，DP101-01<br>
**GST柱**：Glutathione Beads 4FF，天地人和，SA010100<br>

# 摇菌
将质粒转化BL21感受态，涂板子，过夜生长。<br>
挑6-8个克隆，接到15ml Amp+ LB培养基。<br>
将6ml菌液接到1L Amp+ LB培养基中。<br>
240rpm 37℃，OD600到0.8-1.0（约2h）<br>
冰浴降温至低于18℃，加入500ul 1M IPTG <br>
**注**：理论上，IPTG的终浓度，温度，时间应该摸索下，看那种诱导条件蛋白浓度高，纯度高，然后跑个SDS配置胶，考马斯亮蓝染色，脱色。<br>
200rpm 18℃ 16h<br>

# 破菌
5000rpm 30min离心收菌  （此处可以液氮冻存）。<br>
用binding buffer重悬（先加40ml重悬，再用40ml冲洗），超声前混匀（*留样，样品1-菌液）。<br>
55% 功率 3s on 7s off 有效时间3min* 2（总时间10min*2），中间混匀，补充冰。<br>
12000 rpm 4℃ 1h离心，用0.45um滤膜过滤上清液，混匀（*留样，样品2-裂解液）。<br>

# 过柱子

## 平衡柱子
在收细菌之前先平衡Ni柱与GST柱
### Ni柱平衡
若柱子是在ddH2O中保存的: 8倍体积binding buffer
若柱子是在20%乙醇中保存的: 8倍体积 ddH2O + 8倍体积binding buffer

### GST柱平衡
若柱子是在ddH2O中保存的: 8倍体积PBS-DTT
若柱子是在20%乙醇中保存的: 8倍体积ddH2O + 8倍体积 PBS-DTT

## 过Ni柱
样品上柱，4℃旋转20min，冰上静置20min，收集穿出液，（*留样，样品3-Ni穿出）<br>
10倍体积binding buffer洗涤<br>
+0.5h	5倍体积 elution buffer洗脱，注意每流出1ml时，测蛋白浓度<br>
取10μl穿出+10ul快染液，看颜色变化，如果水平低且趋于不变，则停止收样<br>
或用nanodrop测OD280，看吸收曲线，如果水平低且趋于不变，则停止收样<br>
若还有很多样品，则继续洗脱（*留样，样品4-Ni洗脱）<br>
若短时间内还会使用则: 10倍体积ddH2O洗柱，放于4℃<br>
若长时间不用则: 10倍体积binding buffer + 10倍体积ddH2O洗柱 + 10倍体积20%乙醇，储存于20%酒精，放于4℃<br>

## 过GST柱
通过蛋白超滤管将buffer置换为PBS-DTT，超滤管4000rpm 4℃离心.<br>
与重生好的GST beads 4℃旋转孵育2h.<br>
上柱，收穿出（*留样，样品5-GST穿出）.<br>
10倍体积PBS-DTT洗涤.<br>
用3~5倍体积GST elution buffer洗脱.<br>



# 柱子重生

## Ni柱重生
若柱子纯化一个蛋白使用超过三次或用于纯化另一个蛋白，则需要重生: 5倍体积 6M盐酸胍+乙酸 +  10倍体积ddH2O + 5倍体积0.5M EDTA + 10倍体积 ddH2O + 5倍体积 NiSO4 + 10倍体积ddH2O（若短期保存，则留部分液体直接储存于4℃） + 10倍体积20%乙醇（若长期保存，则留部分液体直接储存于4℃）.<br>

## GST柱重生
10倍体积ddH2O洗柱<br>
5倍体积 6M盐酸胍<br>
10倍体积 ddH2O（若短期保存，则留部分液体直接储存于4℃）<br>
10倍体积20%乙醇/PBS（若长期保存，则留部分液体直接储存于4℃）<br>

# 疑问？
1. 蛋白表达为什么要低温诱导？<br>
低温诱导蛋白表达的主要原因是为了减缓蛋白的折叠速度，从而有助于蛋白正确地折叠和形成功能性构象。在低温条件下，蛋白的折叠速度会减慢，使得蛋白分子有更多的时间进行正确的折叠，避免在高温下出现蛋白聚集和不正确折叠的问题。因此，低温诱导可以提高目标蛋白的表达量和纯度。

2. pcDNA3.1也有T7 promoter可以用来转化BL21(DE3)进行蛋白表达么？如果可以，是否需要诱导？表达条件是什么？若不能表达，那T7 promoter在pcDNA3.1中有什么作用？<br>
BL21(DE3)的基因组，带有LacI，所以也可以抑制placUV5启动子，进而抑制T7 RNAP。所以按理说需要IPTG诱导，但是pcDNA3.1等真核表达载体虽然含有T7启动子能和T7RNA聚合酶结合，但是上面没有与原核生物核糖体结合的SD序列，所以在原核生物内核糖体不能识别该质粒，应该不能在原核内表达，真要表达的话可以在T7启动子后面加个SD序列。pcDNA3.1 载体上同时包含 CMV 和 T7 启动子，主要是为了增加载体的多功能性和适用范围，使其不仅能在真核细胞内高效表达，还能用于体外转录、翻译、RNA 标记或编辑等实验。这样的设计提供了更多的实验灵活性，允许研究人员根据具体研究需求选择合适的启动子进行基因表达调控。pcDNA3.1中的T7启动子可以使该质粒在大肠杆菌中利用T7 RNAP进行RNA合成，之后将合成的RNA转染进真核细胞，从而在真核细胞中实现基因的表达。CMV启动子用于驱动基因在真核细胞中的表达，而T7启动子则用于在大肠杆菌中合成RNA，便于后续的真核细胞转染。这种设计使得pcDNA3.1成为一个多功能的表达载体，适用于多种实验目的和条件。

3.为什么要做密码子优化？还有哪些注意事项<br>
密码子优化的目的是为了**提高蛋白表达水平**。因为密码子是具有**偏好性**的，不同生物甚至同种生物不同的蛋白质编码基因,对简并密码子使用频率并不相同。细胞内对应于稀有密码子的tRNA较少，高频率使用这些密码子的基因翻译过程容易受阻，大大降低蛋白表达水平。密码子优化通过增加靶基因翻译效率提高生物体蛋白表达水平。通过**避免稀有密码子，利用偏爱密码子（Preferred codons)、简化mRNA的二级结构、优化重复序列、消除限制酶切位点、调整GC含量**等方法重新设计基因，以提高翻译效率，进而提高蛋白表达水平。有很多密码子优化在线软件可以进行使用。此外，还需要考虑密码子的组合使用效率。通常情况下，考虑到高频和次高频密码子的组合使用效果会更佳。<br>

对于是否需要进行密码子优化有**密码子适应指数(CAI)**来进行评估，通常情况下，**CAI<0.80**被认为需要进行密码子优化。<br>
[铭研生物 CAI分析网站](http://www.merrybio.com.cn/tools/codon-adaptation-index-calculator.html)
[密码子适应指数分析网站](http://www.bioxyz.net/codon-adaptation-index-calculator/index.html)

**mRNA二级结构的影响**：如果mRNA二级结构复杂且稳定，将会影响翻译效率，尤其是序列里有和核糖体结合位点或翻译起始位点互作的序列，会阻止翻译的进行，合理优化翻译起始区的mRNA二级结构，将有效提高目的蛋白表达水平。<br>
**GC含量的影响**：GC含量是影响表达的另一重要因素，相比较AT间的2个氢键，GC间存在3个氢键，所以GC直接影响DNA的稳定性。高GC含量会间接降低蛋白表达量。<br>
**白质表达翻译起始与终止效率的影响**：翻译过程可以分为起始、延伸和终止三段时期。首先，起始阶段的顺利进行决定了蛋白表达量从0到有。对于翻译的起始。高效的延伸阶段决定了蛋白质能够积累的量。如果mRNA有很多成簇的稀有密码子，会不利于核糖体的运动速度，进而降低翻译效率。翻译终止是最容易被忽略的一步。有研究表明终止效率很大程度上影响蛋白表达水平，提高翻译终止效率将会显著提高蛋白表达水平。<br>

# 常见问题及建议
**1.纯化的组分中没有His tag的蛋白?**<br>
1.1 蛋白没有挂上柱
(1)His tag蛋白没有与柱结合：
可能原因是超声功率太大，蛋白炭化;或超声功率太小，蛋白没有释放. **策略**：改变超声功率，并在超声前加入溶菌酶.<br>
(2)组氨酸标签暴露不完全. **策略**：在变性条件下对蛋白去折叠,(用4-8 M脲，或4-6 M 盐酸胍) 进行纯化。<br>
(3)His 标签丢失. **策略1**：WB检查His是否表达，上游载体构建，改变His-tag 的位置(C端或N端)，必要时增加His个数。**策略2**：孵育的时间不够，降低流速和增加孵育的时间。**策略3**：改变螯合的金属离子，寻找到最佳的结合金属离子。<br>
(4)不适合用Ni柱.Ni2+ 通常是从宿主细胞蛋白中纯化大多数6×His 标记的重组蛋白质的最常用离子。蛋白和金属离子之间的结合强度受蛋白长度、His tag位置、亲和标记在蛋白的暴露程度、所用离子的类型、以及缓冲液的pH，因此一些蛋白用其他离子可能更容易地进行纯化而不用Ni2+。<br>
(5) 镍离子脱落.若降低pH来洗脱,当pH低于3.5，会导致镍离子脱落.**策略**：改变洗脱办法，咪唑竞争性洗脱.<br>

1.2 蛋白没有被洗脱下来。<br>
(1) 洗脱条件太温和(组氨酸标记的蛋白质仍然结合在柱上，结合力较强) **策略**：用增加咪唑的梯度洗脱或降低pH 来找出最佳的洗脱条件。
(2)可能样品或binding buffer不正确.**策略**：检测pH 及样品和结合缓冲液的组成份。确保在溶液中鳌合剂或强还原剂的浓度及咪唑的浓度不是太高。<br>
(3) 蛋白已沉淀在柱上. **策略**：减少上样量或使用咪唑的线性梯度而不是分步洗脱以降低蛋白的浓度。试用去污剂或改变NaCl浓度，或在变性条件(去折叠) 下洗脱(用4-8M 脲，或4-6 M盐酸胍)。<br>
(4) 非特异性疏水或其他相互反应. **策略**：加非离子去污剂到洗脱缓冲液(如：2% Triton X-100)或增加NaCl 的浓度。<br>

**2.His 标签蛋白洗脱后杂带较多?** <br>
2.1 蛋白酶降解了部分标签蛋白. **策略**：请添加蛋白酶抑制剂。<br>
2.2 天然蛋白所带His的干扰. **策略**: 采用多步纯化的思路，如利用Strep 标签进行两步纯化或采用Subtractive method 进行纯化。<br>
2.3 杂质和标签蛋白结合在一起. **策略**：在超声破碎细胞之前加入去垢剂或者还原剂;增加去垢剂的浓度( 2% Triton X-100 or 2% Tween 20);或者在Wash buffer 中增加甘油的浓度(50%) 减少非特异性的相互反应;考虑增加咪唑的浓度或者改变金属离子。<br>
2.4 洗涤不充分. **策略**：增加洗涤的次数，使洗涤充分。<br>
2.5 杂质对镍离子有更高的亲和性. <br>
**策略1**：咪唑浓度必须优化，以确保高纯度(宿主细胞蛋白质的低结合) 和高产率(带His tag的目标蛋白质的强结合)之间的最佳平衡。分步或者线性洗脱摸索出最优的咪唑结合和清洗浓度;在样品中加入与结合缓冲液同样浓度的咪唑;咪唑的梯度不大(20 个或更多的柱床体积)，可能分离出有相似结合强度的蛋白<br>
**策略2**：筛选最适合的缓冲液条件，NaCl浓度，pH范围都需要进行筛选。对于单一目标蛋白在进行缓冲液筛选时，将缓冲液、盐、甘油和还原剂设计成不同的混合配方来进行优化。<br>
**策略3**：若以上优化的条件都不能去除杂质蛋白，需要考虑多步纯化的思路。<br>
纯化过程中流速不应该过快。

**3.各个OD600值增殖速度?** <br>
在1L锥形瓶中的增殖速度。<br>
0.26到0.6需要54min<br>
0.6到0.84需要21min<br>
0.66到0.86需要15min<br>
0.2到0.9需要1.5h<br>
0.66到0.88需要30min


