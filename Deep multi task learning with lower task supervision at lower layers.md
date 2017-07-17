# Deep multi task learning with low level tasks supervised at lower levels

By Anders Sogaard from University of Copenhagen

## Abstract
- Earlier all task supervisions were on the same layer. 
- The major contribution of this paper is that if there is a hierarchy present in the tasks that are being done.
- The performance can be improved by using a similar hierarchy in the network. So, supervise the lower level tasks at lower layers.

## Model
- Task: Sequence tagging using deep BiLSTM
### Deep bi-RNNs
- LSTMs are used as a black box function which converts a input x<sub>1..n</sub> to output vector h<sub>n</sub>. 
- The output vector h<sub>n</sub> can be thought to be conditioned on the input x<sub>1..n</sub>
- biRNN can be best summarized as below.
![biRNN.PNG](img/lower-layer-supervision/1.PNG)
- The vector v<sub>i</sub> - BIRNN(x<sub>1..n</sub>) is then a representation of the ith item in x<sub>1..n</sub> taking into account both the entire history x<sub>1..i</sub> and the future x<sub>i..n</sub>.


