# A Joint Many-Task Model: Growing a Neural Network for Multiple NLP Tasks

By Salesforce guys: **Kazuma Hashimoto

## Abstract
- JMT model can be trained end-to-end for POS tagging, chunking, dependency parsing, semantic relatedness, and textual entailment
  -  Higher layers include
shortcut connections to lower-level
task predictions to reflect linguistic hierarchies.
 - predicts increasingly
complex NLP tasks at successively deeper layers.
 - motivated by Søgaard and
Goldberg (2016) who showed that predicting two
different tasks is more accurate when performed in
different layers than in the same layer

![architecture.PNG](1.PNG)

