### Regex

- What is Regex?

  A RegEx, or Regular Expression, is a sequence of characters that forms a search pattern.
RegEx can be used to check if a string contains the specified search pattern.

- Regex 适用范围和局限性？

  Regular expressions play a surprisingly large role
Sophisticated sequences of regular expressions are often the first model for any text processing text

  For many hard tasks, we use machine learning classifiers
But regular expressions are used as features in the classifiers;

  Can be very useful in capturing generalizations
  
 - [Learn Regex by hand](https://www.w3schools.com/python/python_regex.asp)


### Basic Text Processing
What are the task? 

What are the potencial solutions?

#### Tokenisation

- How many words?

  难点：名词所有格，变形（are am be），连字符，大小写，特殊名称，缩写，不同语言有不一样的细节

#### Nomalisation and Stemming

- Source of word variants

  Infection (例如单复数变化，过去式)； Deviation(从名词变形为形容词) ; Compounding (德语非常常见); Clitization(例如缩写) 

- Why do we need Normalization?

  Information Retrieval: Indexed text & query terms must have same form. 为了信息检索，USA和U.S.A其实是一样的

- How to deal with Normalization?

  首先，处理Case folding 大小，然后，处理Morphology词形学。

  i. Stemming
  
  Look-up table\
  Suffix-stripping algorithms\
  Stochastic algorithms.(例如 Porter’s algorithm)
  
  ii. Lemmatization
  
  lemma比stem更严格，lemma还是拼写正确的词汇
  
#### Sentence segmentation and Decision Trees

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
  
  Machine learning methods includes decision tree, logistic regression, SVM, Neural Nets and etc.

#### Minimum Edit Distance

- Why do we need to consider MED?

  用AI预测你喜欢的歌曲，这两首歌曲的曲风需要完全一致吗？\
  当然不用，大概差不多就行，我们需要定义大概差不多是什么意思。

- How similar are two strings?

  spell correction 有时候拼写错误就只是一个字母错误\
  computational biology to align two sequences of nucleotides. 计算生物测算核苷酸序列
  
 - How to define Edit Distance?
 
   The minimum edit distance between two strings. 两个数据之间最小的可编辑的距离。
  
 -   **How to calculate Edit Distance?**

 

 
