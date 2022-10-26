# Assignment 02

Outline

* Task 1 WordNet word similarity
* Task 2 Lesk algorithm
* Task 3 Markov chains

## Task 1 WordNet word similarity

## Task 2 Lesk algorithm

## Task 3 Markov chains

__a) Collecting the counts (3 pts)__

__b) Conditional probabilities (3 pts)__

__c) Most likely word (3 pts)__

__d) Generating text (2 pts)__

__e) Apply the model to a corpus (2 pts)__

* 什么是马尔科夫过程？

  一个马尔科夫过程就是指过程中的每个状态的转移只依赖于之前的n个状态，
  
  这个过程被称为1个n阶的模型，其中n是影响转移状态的数目。
  
  最简单的马尔科夫过程就是一阶过程，每一个状态的转移只依赖于其之前的那一个状态。

* 什么是Markov chain?

  时间和状态都是离散的马尔可夫过程称为马尔科夫链。

  换句话说，你的人生和你过去发生过什么，关系不大，只跟现在和有限的过去相关。
  
  反对弗洛伊德的精神分析法，支持阿德勒个体心理学。
  
  ”人不应该被过去束缚，只有你能描绘自己的未来。“
  
  我是如何将数学学成心灵鸡汤的？来，干了这杯随机过程！

* 什么是无后效性？

  在给定当前信息下，过去对于预测将来是无关的。
  
* 马尔可夫链与文本分析有什么关系？

  马尔科夫链是n-gram模型的基本假设
  
* 什么是链式规则？

  $p\left(w_1, w_2, \ldots, w_m\right)=p\left(w_1\right) * p\left(w_2 \mid w_1\right) * p\left(w_3 \mid w_1, w_2\right) \ldots p\left(w_m \mid w_1, \ldots, w_{m-1}\right)$
  
* 什么是文本语料库 text corpus?
  
  口语或书面语篇的集合
  
* 什么是 n-gram 模型？

  gram是指每一个字节片段
  
  模型假设：第n个词的出现只与前面n-1个词相关，而与其他任何词都不相关，整个句子的概率就是各个词出现的概率的乘积。
  
  概率计算：通过直接从语料中统计n个词同时出现的次数得到。
  
  常用模型：二元bigram，三元trigram
  
* 如何定义Unigram model, Bigram model, Trigram model?

  当 n=1，一个一元模型unigram model为：
  
  $$
  P\left(w_1, w_2, \cdots, w_m\right)=\prod_{i=1}^m P\left(w_i\right)
  $$
  
  当 n=2，一个一元模型bigram model为：
  
  $$
  P\left(w_1, w_2, \cdots, w_m\right)=\prod_{i=1}^m P\left(w_i \mid w_{i-1}\right)
  $$
  
  当 n=3，一个一元模型trigram model为：
  
  $$
  P\left(w_1, w_2, \cdots, w_m\right)=\prod_{i=1}^m P\left(w_i \mid w_{i-2} w_{i-1}\right)
  $$

* 什么是贝叶斯法则？

  如何推断一个人是不是好人，你可以看他做了多少好事。
  
  支持某项属性的事件发生得愈多，该属性成立的可能性愈大。
  
  举个栗子：新冠PCR测试
  
    样本空间：UZH的所有学生
  
    UZH学生为新冠患者的概率是30% （先验概率）
  
    新冠患者PCR检测结果呈阳性的概率是99%
  
    P(A) = 30%, P(B|A) = 99%
  
    求UZH某学生参加一次PCR检测呈阳性时，该学生患病的概率是多少？（后验概率）
  
    $$
    P(A \mid B)
    =\frac{P(B \mid A) P(A)}{P(B \mid A) P(A)+P(B \mid \bar{A}) P(\bar{A})}
    $$
  
    P(A|B) = (99% * 30%)/[ (99%*30%) + (1%*70%)]
  
  
  
  
  

  

  

  
