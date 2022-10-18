
### Wordnet

  * [Wordnet](http://wordnetweb.princeton.edu/perl/webwn)基本功能
  
  ``` js
  sudo pip install nltk % wordnet 是nltk的一个组件
  ```
   ```js
  import nltk
  nltk.download('wordnet')
  ```
  
  Wordnet3.0已经包含了超过15万个词以及20万个词之间的语义关系，成为了目前处理英文最多的一类词典知识库，主要用于**词义消歧**
  
  Wordnet描述了compound(复合词)、phrasal verb(短语动词)、collocation (搭配词)、idiomatic phrase(成语)、word(单词。
  
  其中word是最基本的单位等对象，以及对象之间的关联关系，例如，同义反义关系(synonymy，antonymy)，上下位关系(hyponymy，troponymy)，部分整体关系(entailment，meronymy)。
  
  
