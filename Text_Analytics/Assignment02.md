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
  

  

  

  
