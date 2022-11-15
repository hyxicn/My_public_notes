
# 02 Preprocessing 文本预处理

## 1. 引言
通常情况下，语言数据在使用之前需要对其进行数据清理。

## 1.1 为什么要进行文本预处理

文本预处理（Preprocessing）是大多数NLP应用的第一步，简单来说，它的目的是将文档拆借成单词以便计算机程序能够解释。

## 1.2 定义

文本预处理的方法：

* Regular expression 正则表达式: 匹配，检索和替换那些符合某个模式(规则)的文本
* Tokenizations 分词: 将句子拆分成单词
*  Normalisation 词规范化: 将单词转换为规范形式
   * Stemming 词干提取：抽取词的词干或词根形式
   * Lemmatization 词形还原：把词汇还原为能够表达完整语义的一般形式
* Sentence Segmentation: 句子分割（结合决策树等机器学习模型）

相关定义：

* Type: an element of the vocabulary.
* Token: an instance of that type in running text.

### 2. Regex 正则表达式

* 什么是 RegEx？

  Regular Expression 简写为RegEx

  规则表达式通常被用来匹配、检索和替换那些符合某个模式pattern（规则）的文本等

  A RegEx, or Regular Expression, is a sequence of characters that forms a search pattern. RegEx can be used to check if a string contains the specified search pattern.

- Regex 适用范围和局限性？

  Regular expressions play a surprisingly large role
Sophisticated sequences of regular expressions are often the first model for any text processing text

  For many hard tasks, we use machine learning classifiers
But regular expressions are used as features in the classifiers;

  Can be very useful in capturing generalizations
  
 - [Learn Regex by hand](https://www.w3schools.com/python/python_regex.asp)

### 3. Tokenization 分词

- How many words?

  难点：名词所有格，变形（are am be），连字符，大小写，特殊名称，缩写，不同语言有不一样的细节

### 4. Normalization 词规范化

词规范化：将已经分词的单词转化为正规形式

- Source of word variants

  Infection (例如单复数变化，过去式)； Deviation(从名词变形为形容词) ; Compounding (德语非常常见); Clitization(例如缩写) 

- Why do we need Normalization?

  词规范化的目的：缩小词汇表；将具有相同意义的单词映射为相同的type

  Information Retrieval: Indexed text & query terms must have same form. 为了信息检索，USA和U.S.A其实是一样的

- How to deal with Normalization?

  首先，处理Case folding 大小，然后，处理Morphology词形学。

  i. Stemming 词干提取
  
  Look-up table\
  Suffix-stripping algorithms\
  Stochastic algorithms.(例如 Porter’s algorithm)
  
  ii. Lemmatization 词形还原
  
  lemma比stem更严格，lemma还是拼写正确的词汇

损失的信息：Stemming ＞ Lemmatization

### 5. Sentence Segmentation 句子分割

- 如何划分句子？难点和解决方案是什么？

  - '!, ?' are relatively unambiguous

  - Period “.” is quite ambiguous\
  Sentence boundary\
  Abbreviations like Inc. or Dr.\
  Numbers like .02% or 4.3

  - Build a binary classifier\
  Looks at a “.”\
  Decides EndOfSentence/NotEndOfSentence\
  Classifiers: hand-written rules, regular expressions, or machine-learning

- 对于分类问题有哪些三种常见思路？ 
  - hand-written rules
  - regular expression 
  - machine-learning(推荐)
  
  Machine learning methods includes **decision tree, logistic regression, SVM, Neural Nets** and etc.

### 6. Minimum Edit Distance

- Why do we need to consider MED?

  用AI预测你喜欢的歌曲，这两首歌曲的曲风需要完全一致吗？\
  当然不用，大概差不多就行，我们需要定义大概差不多是什么意思。

- How similar are two strings?

  spell correction 有时候拼写错误就只是一个字母错误\
  computational biology to align two sequences of nucleotides. 计算生物测算核苷酸序列
  
 - How to define Edit Distance?
 
   The minimum edit distance between two strings. 两个数据之间最小的可编辑的距离。
  
 -   **How to calculate Edit Distance?**

 

 
