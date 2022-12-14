# 02\_Foundations 基本定义


Outline:

* Word Senses and Word Relations
* Knowledge Bases
* Word Similarity
* Word Sense Disambiguation

Source:

* [SLP3 Chapter 18](https://web.stanford.edu/\~jurafsky/slp3/18.pdf)

## Words senses

1. How do we know when a word has more than one sense? 

    **Zeugma test**
    
    ### Example
    
    Which flights serve breakfast?
    
    Does Lufthansa serve Philadelphia?
    
    ?Does Lufthansa serve breakfast and Philadelphia?
    
    Since this conjunction sounds weird, we say that these are two different senses of serve.
 
## Words relationships

* Word Relations
  * Homonymy 一词多义
  * Polysemy 近义词
  * Metonymy [转喻](https://www.zhihu.com/question/19766649)
  * Synonyms 同义词
  * Antonyms 反义词
  * Autoantonyms 自反意词
  * Hyponymy and Hypernymy 上下位关系
    * Hyponym/Subordinate
    * Hypernym/Superordinate 
  * Meronymy and Holonymy 部份整体关系
    * Meronym 部份
    * Holonym 整体

  ### Examples

  * Car is a **hyponym** of vehicle.
  
  * Vehicle is a **hypernym** of car.
  
  * Wheel is a **meronym** of car, and car is a **holonym** of wheel.
 
  ### Causion
  
  * There are almost NO perferct synonymy examples. (large ≠ big in all sentences.
  
  * Synonymy is a relation between senses rather than words.
  
## Knowledge Base

* [WordNet](https://web.stanford.edu/~jurafsky/slp3/19.pdf)
* [ConceptNet](https://conceptnet.io/)
* [FrameNet](https://web.stanford.edu/~jurafsky/slp3/20.pdf)

## Word Similarity

* Task: Identify synonymy

  We can compute similarity over both words and senses.
  
  Solution: Two classes of similarity algorithms
  
  **Undertand the idea, pros and cons for each algorithms!**
  
  * Thesaurus-based algorithms:
  
    * Path based similarity
    
  * Distributional algorithms:
    
    * Resnik
    * Dekang-Lin
    * eLesk
  
  ### Path based similarity
  ### Resnik
  ### Dekang-Lin
  ### eLesk

## Word Sense Disambiguation

  Reference:
  
  * [SLP3 Chapter 7](https://nlp.stanford.edu/fsnlp/wsd/)
  
  * [SLP3 Chapter 4](https://web.stanford.edu/~jurafsky/slp3/4.pdf)
  
  **Task of WSD:**
  
   Given a word in contex and a fixed inventory of potencial word senses. Decide which sense of the word this is?

   ### Supervised Machine Learning
   
   * Task: Classification
      
   * Methods: Any kind of classifier
      
      * Naive Bayes
        
      * Logistic Regression
        
      * Neural Networks
        
      * Support-vector machines
        
      * k-Nearest 
   
   ### Thesaurus/Dictinary Methods
   
   * Methods: 
   
      * The simplified Lesk algorithm
      
      * The corpus lesk algorithm
      
      * Graph-based methods
   
   ### Semi-supervised Learning(not covered)
   


  
