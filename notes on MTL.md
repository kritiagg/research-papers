# Summary on Multi Task Learning for NLP

## Motivation
- Acts as a regularizer
- Suitable if not much data for some task
- Some patterns might be difficult to learn using a particular task and easier for some other task
- Biases the model towards a presentation that other tasks also prefer.

## Experiments experiments..
### Training protocols:
- Alternate training: 
  - Choose a random training example and task, compute the loss and back propagate till the current task layer.
  - Might create a bias towards the task with bigger dataset.
  - easiest to implement
  - used by lower layers supervision paper
  - mostly used when different dataset (Hence useful for EQnA task)
- Joint training 
  - as in Joint multi task training paper
    - train all the tasks at different layers
    - back propagate from the task layer to the embeddings?
  - Weighted average of the tasks
  
### Different embeddings: 
  - Senna embeddings used for POS and chunking tasks
  - Glove : used by RNet, BiDAF, Match LSTM papers
  - word2vec: Joint multi training paper used skip gram version of word2vec with n-gram char embeddings
    - https://www.tensorflow.org/tutorials/word2vec
    - Word2vec is a particularly computationally-efficient predictive model for learning word embeddings from raw text. It comes in two flavors, the Continuous Bag-of-Words model (CBOW) and the Skip-Gram model (Section 3.1 and 3.2 in Mikolov et al.). Algorithmically, these models are similar, except that CBOW predicts target words (e.g. 'mat') from source context words ('the cat sits on the'), while the skip-gram does the inverse and predicts source context-words from the target words. This inversion might seem like an arbitrary choice, but statistically it has the effect that CBOW smoothes over a lot of the distributional information (by treating an entire context as one observation). For the most part, this turns out to be a useful thing for smaller datasets. However, skip-gram treats each context-target pair as a new observation, and this tends to do better when we have larger datasets. We will focus on the skip-gram model in the rest of this tutorial.
    - Hence, for large datasets, if you are using word2vec use it with skip gram model.
  - skip gram vector: might be suitable for sentences too : used by Joint multi training POS, Chunking, etc.
### Hard parameter sharing vs soft parameter sharing
  - Hard parameter sharing: easier to implement
  - Soft parameter sharing: harder to implement
    - regularize the distance between the parameters of the model (l2)
### Different depth different tasks:
  - low level tasks like EQnA at lower levels and higher level tasks ranker and extractor on the same high level
  - Experiment with ranking and extracting at different levels
### Auxilliary tasks
  - More auxilliary tasks can be added which might help the main task
  - 
### Regularization
- Change the Loss function or objective function in old papers (BiDAF etc.) to include L2 regularization 
  - and/or successive regularization term 
  - or add Dropout layers

### Similarity task EQnA :
  - Attention layer captures similarity, perhaps we can use it for EQnA or just use KL divergence loss functions.
  - Siamese networks
  - Match LSTM

### Models and Architectures:
- Pass lower layer outputs directly to upper layers as in Joint Multi task training
- Dynamic memory networks: multiple hops in BiDAF
- Deep Relationship Networks: hard parameter sharing 
  - Task specific layers
  - Cons: pre-defined sharing structure which is not well defined for NLP
 - Fully adaptive feature learning: difficult as its a dynamic network

## What's next?
- alternate training
- Joint training
