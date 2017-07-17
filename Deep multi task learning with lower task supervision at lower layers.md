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
- biRNN can be best summarized as above.
![biRNN.PNG](img/lower-layer-supervision/1.PNG)
- The vector v<sub>i</sub> - BIRNN(x<sub>1..n</sub>) is then a representation of the ith item in x<sub>1..n</sub> taking into account both the entire history x<sub>1..i</sub> and the future x<sub>i..n</sub>.
- Finally in a deep bi RNN, both RNN<sub>F</sub> RNN<sub>R</sub> are k-layered RNNs.

### Greedy sequence tagging with deep bi-RNNs
- In a sequence tagging task, we are given an input
w1, · · · , wn and need to predict an output
y1, · · · , yn, yi ∈ [1, · · · , |L|], where L is a label
set of interest; i.e., in a POS tagging task, L is
the part-of-speech tagset, and yi
is the pos-tag for
word wi
.
- If we take the inputs x<sub>1:n</sub> to correspond to a
sequence of sentence words w1, · · · , wn, we can
think of v<sub>i</sub> = BIRNN(x<sub>1:n</sub>, i) as inducing an in-
finite window around a focus word w<sub>i</sub>.

- We can then use v<sub>i</sub> as an input to a multiclass classification
function f(vi), to assign a tag yˆi to each input
location i.
- The tagger is greedy: the tagging decisions
are independent of each other. 
- However, as shown below and in other recent work using
bi-RNNs for sequence tagging, we can still produce
competitive tagging accuracies, because of
the richness of the representation vi
that takes the entire input sequence into account.


For a k-layer bi-RNN tagger we get:

tag(w1:n, i) = ˆyi = f(v<sup>k</sup><sub>i</sub>)

v<sup>k</sup><sub>i</sub> = BIRNNk(x1:n, i)

x1:n = E(w1), E(w2), · · · , E(wn)

where E as an embedding function mapping each
word in the vocabulary into a demb-dimensional
vector, and v<sup>k</sup><sub>i</sub>
is the output of the k-th BIRNN layer
as defined above.





