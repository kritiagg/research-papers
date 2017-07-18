# Summary on MTL

## Experiments experiments..
### Training protocols:
- Alternate training: 
  - Choose a random training example and task, compute the loss and back propagate till the current task layer.
  - easiest to implement
  - used by lower layers supervision paper
  - mostly used when different dataset (Hence useful for EQnA task)
  
### Different embeddings: 
  - Senna embeddings used for POS and chunking tasks
  - word2vec and Glove : used by RNet, BiDAF, Match LSTM papers
  - skip gram vector: might be suitable for sentences too : used by Joint multi training POS, Chunking, etc.
### Hard parameter sharing vs soft parameter sharing
  - Hard parameter sharing: easier to implement
  - Soft parameter sharing: harder to implement (unclear too!)
### Different depth different tasks:
  - low level tasks like EQnA at lower levels and higher level tasks ranker and extractor on the same high level
  - Experiment with ranking and extracting at different levels
### Auxilliary tasks
  - More auxilliary tasks can be added which might help the main task
  - 
### Regularization
- Change the Loss function or objective function to include L2 regularization 
- and/or successive regularization term 
- or add Dropout layers

### Similarity task EQnA :
  - Attention layer captures similarity, perhaps we can use it for EQnA or just use KL divergence loss functions.
  - Siamese networks
  - Match LSTM

### Models and Architectures:
- Pass lower layer outputs directly to upper layers as in Joint Multi task training
- Dynamic memory networks: multiple hops in BiDAF
- 

## What's next?
- alternate training
- 
