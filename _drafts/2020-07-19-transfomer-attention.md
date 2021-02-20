---
layout: post
title: What I learned from Attention Is All You Need - Transfomer and Attention
mathjax: true
---

### Attention
Given a query and a set of key - value pairs (you can think of this as a dictionary), we want to get the output. Attention is the mapping from input to output.

In the paper they use scaled dot-production attention

$$Attention(Q,K,V)=softmax(\frac{QK^T}{\sqrt{d_k}})V$$

### Self-attention
Normally the attention function is used in the encoder-decoder architecture, where the decoder can attend to the output from the encoder. In this case the Key - Value pairs come from the encoder, while the Query comes from the decoder. 

Self-attention is the attention query the Query and the Key - Value pairs both come from the same place (from encdoer or decoder). (Get an example for NLP). 

### Multi-head attention
Instead of perform one single scaled dot product attention, in multi-head attention we have multiple attention running in parallel. Each attention is called a "head".

### Transformer
Transformer is introduced to replace the need of concurence operation. In encoder and decoder it use self-attention to capture the dependencies between words in the input sentences and target sentences. This is similar to using recurrent neural network on the inputs. Then, it use multi-head attention to represent the relationship between the decoder and encoder.
They positional encoding to represent the relative of positions in the sequence.

### Why Transformer works so well
1. Less computation
2. Better in capturing the long-range dependencies. In tradition GRU or LSTM. We use the common forward - backward propagation. The training signal must go through the whole sequence. The longer the sequence, the harder it is for the network to compute the dependencies between positions. Transformer replace the need for recurrent computing. 
