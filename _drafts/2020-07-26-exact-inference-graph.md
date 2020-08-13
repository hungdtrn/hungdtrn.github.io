---
layout: post
title: Exact Inference in Graphical Model
mathjax: true
---

1. Factor graph
    - Undirected graph
    - Have two types of node:
        - Circle node: Variables
        - Square node: Factors / Link between two nodes
    - Why factor graph
        - Both directed and undirected can be converted to factor graph
        - Remove the loop in undirected graph. Why?
            - Make it hard for message passing. If there is a loop. When we eliminate a node, the whole graph structure change. 
        - Why don't we compute on directed graph?
            - It is a general case of Viterbi algorithm
2. Sum-product algorithm
    - Iterative, dynamic algorithm
    - Two type of message passing:
        - From factor to node. The factor first collect information from all of connected nodes (except the destination node), and send to the destination node

        $$\mu_{f_{s}\rightarrow x}(x)=\sum_{x_{1}}\sum_{x_{2}}...\sum_{x_{M}}f(x,x_{1},x_{2},...,x_{M})\prod_{m\in ne(f_{s})\backslash x}\mu_{x_{m}\rightarrow f_{s}}(x_{m})$$

        - From node to factor. Similarly, a node might connect to several factor. Before sending a message to the destination factor, the node need to collect all messages comming from other connected factors

        $$\mu_{x\rightarrow f_{S}}=\sum\mu_{f_{S'}\rightarrow x}$$

        - For leaf node.

        $$\mu_{x_{m}\rightarrow f_{s}}(x)=\prod_{l\in ne(x_{m})\backslash f_{s}}\mu_{f_{l}\rightarrow x_{m}}(x_{m})$$

    - Start at leaf node, the aggregate messages all the way up to the desired node
    - The described algorithm compute probability at one node. How about computing the probability of all nodes?
        - Forward and backward

3. Simple example in the book
4. Max - sum algorithm
    - Now we want to find the maximum probability of the joint distribution as well as the set of variables that gives that probability.
    - Consider undirected graph:

    $$\underset{x}{\max}p(x)=\frac{1}{Z}\underset{x_{1}}{\max}...\underset{x_{N}}{\max}[\psi_{1,2}(x_{1},x_{2})...\psi_{N-1,N}(x_{N-1},x_{N})]$$

    $$\underset{x}{\max}p(x)=\frac{1}{Z}\underset{x_{1}}{\max}\left[\underset{x_{2}}{\max}\psi_{1,2}\left[(x_{1},x_{2})\left[...\underset{x_{N}}{\max}\psi_{N-1,N}(x_{N-1},x_{N})\right]...\right]\right]$$
