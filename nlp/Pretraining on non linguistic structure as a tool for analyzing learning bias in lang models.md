[https://arxiv.org/pdf/2004.14601.pdf]

## Notes:
- How do these sytems give rise to syntax?
- This paper : probes the structural features encoded in language model by evaluating its ability to leverage them for transfer across languages and data types like music etc.
- Train LM on multiple types of data and then test on language to see what type of data generalizes the best for the language.
- Finding the representations that work the best across languages.
- The test for the generalizability is done by the following:
![images/probe.PNG]
- The various training schemes done were:
![images/examples.PNG]
- What is interesting is that the last two experiments with two types of parenthesis lead to similar results. As in even when there was no hierarchy in the second set of paranthesis based lang, it was enough for the model to learn that what starts and the same token ends.
