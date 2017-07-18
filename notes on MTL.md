# Summary on MTL

## Some insights

### When to use Alternate training?
- When we have different datasets for different tasks


## Experiments experiments
### Different embeddings: 
  - Senna embeddings used for POS and chunking tasks
  - skip gram vector: might be suitable for sentences too
### Hard parameter sharing vs soft parameter sharing
  - Hard parameter sharing: easier to implement
  - Soft parameter sharing: harder to implement (unclear too!)
### Different depth different tasks:
  - low level tasks like EQnA at lower levels and higher level tasks ranker and extractor on the same high level
  - Experiment with different tasks
### Auxilliary tasks
  - 
### Regularization
- Change the current Loss function or objective function to include L2 regularization and successive regularization term or add Dropout layers
### Similarity task EQnA :
  - Attention layer captures similarity, perhaps we can use it for EQnA or just use KL divergence loss functions.
  - Siamese networks
  - Match LSTM

### Models and Architectures:
- Pass lower layer outputs directly to upper layers
- Dynamic memory networks: multiple hops in BiDAF


## What's next?
- alternate training
- 
