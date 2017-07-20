# How to do efficient Multi task learning for the tasks: answer extraction, ranking?

## What are we trying to solve:
The task is to answer a query from a set of selected documents. Input is a query and some documents. We have preprocessed the data to create 
passages that can be fed to the model. We now need to figure out a way to calculate the answer passage.

## Challenges:
- What should be the choice of model?
- What are the auxilliary tasks that can be used?

## Some sample auxilliary tasks:
- Query selection (we are already doing query extraction)
- multi topic classification of the passages 
- similarity analysis of 2 passages
- find if a given question is answered by the query
- readability of the passage
- metadata: how many a url was clicked before?
- similar queries 



