# LASER multilingual sentence embeddings
[https://engineering.fb.com/ai-research/laser-multilingual-sentence-embeddings]
[https://arxiv.org/pdf/1812.10464.pdf]
## Notes:
- It has decoder-encoder architecture as in other seq-to-seq models trained for Machine language translation task.
- One shared encoder for all input languages and a shared decoder for generating output language.
- Encoder : 5 layer bi directional LSTM network. The output is a sentence embedding in 1024 dimension fixed size vector, by max pooling over the last states of BiLSTM.
- Decoder : initialized by the sentence embeddings from the encoder, i.e. these are concatenated to each time step of the decoder time step
  -- Decoder needs the language to be decoded in, which is also concatenated with each time step.
- Use shared BPE by concatenation of all languages data, they have different tokenization for each languages.
- Trained only with public parallel data of English and Spanish.
- Improved performance with more languages addition. Trained finally with 93 languages with various different SOV/SVO/VSO (V:Verb, O:Object,S:Subject)

