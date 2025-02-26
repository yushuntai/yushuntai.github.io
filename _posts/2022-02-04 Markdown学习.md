---
layout: post
title:  " Markdown学习"
tags: 实验方法与科研小技巧
date:   2022-02-04
categories: Front-end JavaScript
excerpt: 实验方法与科研小技巧
---


**目录：**

* content
{:toc}




# Markdown的介绍

Markdown 是目前互联网上最流行的写作语言，它使用一些简单的符号（* / ` > [] () #）来标记文本格式，是一种轻量级标记语言。它的语法简洁、格式优美并且有强大的软件支持。创始人是约翰·格鲁伯（John Gruber）。
Markdown可以让人们使用易读易写的纯文本格式编写文档，然后转换成有效的 HTML 文档。Markdown的使用者众多，GitHub，简书，Stack Overflow，Apollo，Moodle，Reddit等等，Markdown可生成包括HTML、PDF、WORD、PPT等各种形式的内容。GitHub上的README.md文件就是Markdown文件，因为md是Markdown的后缀。写README.md文件的时候是可以使用Markdown语法的。


## **常用的Markdown编辑器**
这个好多啦，我比较推荐Typora，当然我们主推的是Rstudio(~~因为其他的我也没用过~~)。


## **学习R Markdown的准备工作**

### 第1步：首先需要下载R和R studio
使用 R markdown 需要先安装 R 包 rmarkdown、knitr 和 caTools，命令为 install.packages(c('rmarkdown', 'knitr', 'caTools'))

### 第2步：设置默认编码方式为 UTF-8
打开 Rstudio然后Tools -> Global Options -> code -> Saving ->Default text encoding -> Change -> UTF-8 -> OK
之前碰到过点击OK无反应的情况，重新关掉Rstudio，及打开的各种Rstudio文件，重新再次打开再次设置就可以了

### 第3步：设置编译引擎
打开 Rstudio然后Tools -> Global Options -> Sweave -> Typeset LaTeX into PDF using: 这一项右侧的下拉菜单中选择 XeLaTeX，保存退出。


## **R Markdown的使用**  
打开Rstudio -> 点击左上角File下的+ -> 点击R Markdown -> 直接点OK就可以(title可以在R Markdown里面改)
R Markdown的YAML header最好不要出现汉字，容易报错。




# **学习内容**


## **知识点1 ——YAML header的介绍**

```{r eval=FALSE}

title: "R Markdown学习笔记"
author: "**余顺太记**"
date: "**今天日期**：`r format(Sys.time(), '%Y-%m-%d')`"  #这里可以显示实时日期

params:   
    n: 100    
    d: !r Sys.Date()  #这里设计个params，后面可直接引用实时日期。  比如：今天的实时日期是： `r params$d`

output: 
  html_document:
    toc: yes  #output后面的:后直接点enter键，输入html_document后加:然后直接点enter键，输入toc: yes即可，注意toc:和yes之间有一个空格。在Typora生成目录的时候想在哪里生成目录，直接在那里输入[TOC]即可
```


今天的实时日期是： `r params$d`




## **知识点2 ——标题**

```{r eval=FALSE}
# 一级标题
## 二级标题
### 三级标题
...
###### 六级标题
```
# 一级标题

## 二级标题

### 三级标题

#### 四级标题

##### 五级标题

###### 六级标题


## **知识点3 ——字体**

```{r eval=FALSE}
**加粗**
*斜体*
***斜体加粗***
~~删除线~~
```
**加粗**  
*斜体*  
***斜体加粗***  
~~删除线~~    


## **知识点4 ——分行**
```{r eval=FALSE}
窗前明月光  #点击Tab键两次，再点击enter键一下，可以起到分行作用。  
疑是地上霜  
举头望明月  
低头思故乡
```
窗前明月光    
疑是地上霜    
举头望明月    
低头思故乡


## **知识点5 ——首行缩进**
```{r eval=FALSE}
首行不缩进。
&nbsp;首行缩进1/4字符。
&ensp;首行缩进1/2字符。
&emsp;首行缩进1个字符。

```
首行不缩进。    
&nbsp;首行缩进1/4字符。   
&ensp;首行缩进1/2字符。   
&emsp;首行缩进1个字符。


## **知识点6 ——文字或图片居中**
```{r eval=FALSE}
第一行文字不居中。 
<div align=center>  #开始居中
第二行文字要居中。    
第三行文字还居中。
</div>              #居中结束
第四行文字不居中
```

第一行文字不居中。 
<div align=center>
第二行文字要居中。    
第三行文字还居中。
</div>
第四行文字不居中。











## **知识点7 ——使部分内容不显示**

```{r eval=FALSE}
---
这一部分内容将不显示
---
```
---
这一部分内容将不显示
---


## **知识点8 ——分割线**


```{r eval=FALSE}
****
这部分内容上下都有分割线，上面和下面的星号数量大于3，并且和下面的星号还要隔一行 

****
```

*****
这部分内容上下都有分割线，上面和下面的星号数量大于3，并且和下面的星号还要隔一行

****

****
****
****
****
****



## **知识点9 ——图片插入**     

**备注：**最好将图片都上传到图床，引用图片使用图床网址，然后markdown发给别人，别人也能打开。如果使用的图片是保存在自己电脑上的，首先图片比较占电脑内存，其次使用markdown发给别人别人也打不开。

必应搜索 **路过图床**，点进去就可以登录（用百度搜不到路过图床的，垃圾百度！）
也可以通过网址登录，路过图床网址： https://imgchr.com/

```{r eval=FALSE}
![]()      #[]里面写名字，()里面写图片地址，可以是本地图片，也可以是网上图片。
![我和向东](D:\photo\我和向东.jpg)  #这个是本地图片的插入
<div align=center>  #开始居中
春天的博雅塔被繁花簇拥  
![博雅塔](https://dpic.tiankong.com/k3/ua/QJ8144360721.jpg?x-oss-process=style/794ws)      
</div>  #居中结束
#这个网址是鼠标点到图片上之后，右键，复制链接地址
```
我在复旦读硕士的时候，向东来找我玩  
![我和向东](D:\photo\我和向东.jpg)  

<div align=center>  
春天的博雅塔被繁花簇拥  
![博雅塔](https://dpic.tiankong.com/k3/ua/QJ8144360721.jpg?x-oss-process=style/794ws)      
</div>

## **知识点10 ——特殊字符**
```{r eval=FALSE}
$\alpha$,$\beta$，$\gamma$，$\theta$，$\sigma$，$\varepsilon$
```
$\alpha$,$\beta$，$\gamma$，$\theta$，$\sigma$，$\varepsilon$


## **知识点11 ——计算公式**
```{r eval=FALSE}
$T=\frac{\bar{x}-\mu}{S/\sqrt{n}}$
```
$T=\frac{\bar{x}-\mu}{S/\sqrt{n}}$






## **知识点12 ——超链接**
超链接使用<>将网址括起来
```{r eval=FALSE}
余顺太-码云Gitee<https://gitee.com/yu_shun_tai/dashboard/projects>  #文字和网址都会显示出来
[余顺太-码云Gitee](https://gitee.com/yu_shun_tai/dashboard/projects)  #只显示文字部分
```

余顺太-码云Gitee<https://gitee.com/yu_shun_tai/dashboard/projects>  
[余顺太-码云Gitee](https://gitee.com/yu_shun_tai/dashboard/projects)



## **知识点13 ——代码块**

有三种方法

### 方法1 ：点击Rstudio的Insert，再选R，同时在{r }里面点Tab键有很多选项可选
点击Rstudio右上角Insert
选项1：eval=FALSE 这一部分代码不运行  
\```{r eval=FALSE}  
\```


选项2:echo=FALSE不输出代码，只输出代码运行结果  
\```{r echo=FALSE}  
\```


选项3:warning=FALSE如果有警告信息，不要输出  
\```{r warning=FALSE}  
\```


### 方法2：自己输入
另一种是先输入\```，然后换行，再输入\```，(注意要在英文输入法下输入)  
\```  
\```

### 方法3：代码区块

```中间书写代码内容```









## **知识点14 ——引用**
```{r eval=FALSE}
>引用的内容
                #中间需要间隔一行
>>一级嵌套引用

>>>二级嵌套引用
```
>引用的内容   

>>一级嵌套引用 

>>>二级嵌套引用


## **知识点15 ——列表**
```{r eval=FALSE}
+ 有序列表第一行      #.之后有一个空格，+-*都可以
+ 有序列表第二行  

* 有序列表第一行  
* 有序列表第二行

- 有序列表第一行  
- 有序列表第二行

* 母列表             #分行之后点两下Tab键
    * 一级子列表
        * 二级子列表
            * 三级子列表

```
+ 有序列表第一行      #.之后有一个空格，+-*都可以
+ 有序列表第二行  

* 有序列表第一行  
* 有序列表第二行

- 有序列表第一行  
- 有序列表第二行


* 母列表
    * 一级子列表
        * 二级子列表
            * 三级子列表


## **知识点16 ——表格**    

**备注：**markdown里面画表格不太方便，可以在Excel里面将表格做好，然后直接拷进Typora，表格就会被解析成源代码，然后再将源代码拷近Rmarkdown就可以了，不需要用手敲表格，那样样会很慢。注意excel中做的表格不能直接拷进Rmarkdown，那样会无法解析。    

```{r eval=FALSE}
|姓名|性别|语文成绩|数学成绩|英语成绩|思想品德成绩|
|:---:|:---:|:---:|:---:|:---:|:---:|
|宋江|男|90|61|88|2|
|鲁智深|男|83|96|40|98|
|武松|男|80|80|80|78|
|卢俊义|男|90|96|70|60|
|李逵|男|0|3|0|0|9|
|扈三娘|女|79|66|76|40|
```

|  姓名  | 性别 | 语文成绩 | 数学成绩 | 英语成绩 | 思想品德成绩 |
| :----: | :--: | :------: | :------: | :------: | :----------: |
|  宋江  |  男  |    90    |    61    |    88    |      2       |
| 鲁智深 |  男  |    83    |    96    |    40    |      98      |
|  武松  |  男  |    80    |    80    |    80    |      78      |
| 卢俊义 |  男  |    90    |    96    |    70    |      60      |
|  李逵  |  男  |    0     |    3     |    0     |      0       |
| 扈三娘 |  女  |    79    |    66    |    76    |      40      |




一些特表的表格可以使用html语法，如下所示：

```
<table>
    <tr>
        <td>引物名称</td>
        <td>序列(5’  to 3’)</td>
        <td>碱基数</td>
        <td>Tm</td>
        <td>PCR时使用的Tm</td>
    </tr>
    <tr>
        <td>M1diUb-S65A PF</td>
        <td>CCAAAAGGAAGCAACGCTGCACCTGGTCCT<br/>GCGTCTG
        <td>37</td>
        <td>70.76℃</td>
        <td rowspan="2">71℃和73℃</td>   #rowspan="2"表示这一部分占两行
    </tr>
    <tr>
        <td>M1diUb-S65A PR</td>
        <td>GGTGCAGCGTTGCTTCCTTTTGGATGTTGTA<br/>ATCGGACAGAGTACGGCC</td>
        <td>49</td>
        <td>71.45 ℃</td>
    </tr>
    </tr>
</table>
```






<table>
    <tr>
        <td>引物名称</td>
        <td>序列(5’  to 3’)</td>
        <td>碱基数和Tm</td>
        <td>Tm</td>
        <td>PCR时使用的Tm</td>
    </tr>
    <tr>
        <td>M1diUb-S65A PF</td>
        <td>CCAAAAGGAAGCAACGCTGCACCTGGTCCT<br/>GCGTCTG
        <td>37</td>
        <td>70.76℃</td>
        <td rowspan="2">71℃和73℃</td>   
    </tr>
    <tr>
        <td>M1diUb-S65A PR</td>
        <td>GGTGCAGCGTTGCTTCCTTTTGGATGTTGTA<br/>ATCGGACAGAGTACGGCC</td>
        <td>49</td>
        <td>71.45 ℃</td>
    </tr>
    </tr>
</table>


```
<table>
    <tr>
        <td>引物名称</td>
        <td>序列(5’  to 3’)</td>
        <td colspan="2">碱基数和Tm</td>   #colspan="2表示这一部分占两列
        <td>PCR时使用的Tm</td>
    </tr>
    <tr>
        <td>M1diUb-S65A PF</td>
        <td>CCAAAAGGAAGCAACGCTGCACCTGGTCCT<br/>GCGTCTG
        <td>37</td>
        <td>70.76℃</td>
        <td rowspan="2">71℃和73℃</td>
    </tr>
    <tr>
        <td>M1diUb-S65A PR</td>
        <td>GGTGCAGCGTTGCTTCCTTTTGGATGTTGTA<br/>ATCGGACAGAGTACGGCC</td>
        <td>49</td>
        <td>71.45 ℃</td>
    </tr>
    </tr>
</table>
```



<table>
    <tr>
        <td>引物名称</td>
        <td>序列(5’  to 3’)</td>
        <td colspan="2">碱基数和Tm</td>
        <td>PCR时使用的Tm</td>
    </tr>
    <tr>
        <td>M1diUb-S65A PF</td>
        <td>CCAAAAGGAAGCAACGCTGCACCTGGTCCT<br/>GCGTCTG
        <td>37</td>
        <td>70.76℃</td>
        <td rowspan="2">71℃和73℃</td>
    </tr>
    <tr>
        <td>M1diUb-S65A PR</td>
        <td>GGTGCAGCGTTGCTTCCTTTTGGATGTTGTA<br/>ATCGGACAGAGTACGGCC</td>
        <td>49</td>
        <td>71.45 ℃</td>
    </tr>
    </tr>
</table>



## **知识点17 ——脚注**
```{r eval=FALSE}
谁言寸草心，报得三春晖。[^1]    #脚注随便是什么都可以，但是要保证跟后面注释一致。自动排序，最后都是数字。排序以前面的为准。
会当凌绝顶，一览众山小。[^A]    
千淘万漉虽辛苦，吹尽狂沙始到金。[^甲]

[^1]: 《游子吟》 孟郊  #上面顺序是1A甲，最后会变成123，注释顺序是1甲A，最后也会变成123的顺序，并且自动会置于文档尾部。
[^甲]: 《杂曲歌辞·浪淘沙》 刘禹锡
[^A]: 《望岳》 杜甫

```

谁言寸草心，报得三春晖。[^1]    
会当凌绝顶，一览众山小。[^A]    
千淘万漉虽辛苦，吹尽狂沙始到金。[^甲]   

[^1]: 《游子吟》 孟郊
[^甲]: 《杂曲歌辞·浪淘沙》 刘禹锡
[^A]: 《望岳》 杜甫


## **知识点18 -DT::datatable函数的使用**

DT::datatable比head要好，因为可以看到全貌。可以去我的markdown《mRNA-seq-expression-load-qc-normalization-DEG-annotation》去看一下该函数的实际应用，非常高逼格。




## **有待学习的内容**

图片大小的更改    
如何出现很多空行


## **知识点19 Typora设置文字颜色/大小/字体属性**
markdown没有直接的语法支持文字的颜色，大小，字体等属性的设置，但是Typora支持html语法，可直接使用html代码：

```{r eval=FALSE}
<span style='color:文字颜色;background:背景颜色;font-size:文字大小;font-family:字体;'>文字</span>

<span style='color:文字颜色;'>文字</span>  #仅设置字体颜色
```




## **知识点20——typora转思维导图**



typora编辑好之后——**文件**——**导出**——**OPML**——保存——打开幕布——新建——导入OPML——选择OPML文件(点完之后看起来没反应，但是已经打开了，将光标放到下面可以看到！)——生成思维导图即可。




## **应该看看的文章**
《Markdown编辑器 --Typora 用法大全》 https://www.jianshu.com/p/a97b48fa8608
《Markdown For Typora 中文版使用指南》 https://zhuanlan.zhihu.com/p/39872673
《markdown神器 -Typora使用教程笔记》https://blog.csdn.net/WeiDelight/article/details/81011921)
《typora-学符号》https://blog.csdn.net/wait_for_eva/article/details/84307306
《史上最完美的 Typora 教程》https://blog.csdn.net/cris_zz/article/details/82919401#1_45
《CSDN-markdown编辑器语法——字体、字号与颜色》https://blog.csdn.net/testcs_dn/article/details/45719357
《markdown emoji表情代码》https://blog.csdn.net/sunhwee/article/details/100110386



****
## ****寄语未来****

****
没有白费的功夫    
脚踏实地    
一步一步向前    
一定会慢慢变好
