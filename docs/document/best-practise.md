# 最佳操作实践

阅读此节之前，确保你至少看过[Demo 使用指南](/document/demo-usage.md)

## 文言仿真加密

下面列出一些情况下的最佳实践。

### 仿真随机性

用户可以通过滑条来选择句式的随机程度。
如果想增强句子逻辑性，那么请调整至"长句优先"，挑选句式的时候会优先使用最长的可用句，但加密随机性可能受影响。

如果想要更随机，语块长短不一的密文，则推荐选择“适中”或更高。

### 通顺

如果嫌生成的句子过于生硬，不妨多次尝试生成(多点几下加密)，选择一个看起来最好的密文。  
只要密钥和原文相同，生成出的所有密文均可以正常解密。

### 逻辑优先密文

如果想要尽可能生成逻辑上最佳的密文，请打开**逻辑**模式。  
然后将随机性滑条拖到最左侧(0)。

如此可以尽量使密文由尽可能多的转折/逻辑复合句式构成。  
能够达到最大程度的，逻辑意义上的以假乱真。

### 效率优先密文

如果想要尽可能生成短的密文，请打开**骈文**模式。  
然后将随机性滑条拖到最左侧(0)。

如此可以尽量使密文由尽可能多的四字/五字骈文句式构成。  
在增强密文文言风格的同时，提升密文的载荷比，使密文缩短。

### 混合模式

如果不作任何特殊设置，仿真算法会参考概率随机组句。  
如此生成的密文随机性更强，适合一般情况下的使用。

### 与上下文搭配

合适的做法是将加密出来的文言文与上下文搭配。  
这么做可以抵抗多种攻击，也让 BERT 之类的模型难以对文本进行分类。

## 传统模式加密

下面列出一些情况下的最佳实践。

### 安全优先

如果你需要最高的安全性，则在加密时设置一个尽可能长和复杂的密码。

最好勾选“去除标志”，来提升密文随机性。

解密时将需要对方勾选强制解密。

### 效率优先

你可以不填密码，这将会使程序自动用内部的默认密码`ABRACADABRA`加/解密。

把密文的识别交给标志位，这么做可以让他人很方便地解密。

## 密文的合适长度

不建议生成过长的密文。

过长的密文(>150 字)，在逻辑上难以形成链条，在句式上可能出现雷同，在字频上可能出现特征。
因此不推荐将大段文章丢进加密器加密。

## 填写密码

如果你不填写密码(`魔咒`)，则程序会自动使用 `ABRACADABRA` 作为密钥来加密。

如果你正在公开平台上发布密文，你可以不填密码。

但如果你想限制某些人解密，或者对密文的安全性有要求，则建议你填写密码。
