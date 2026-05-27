+++
title = "Post with Mathematical Expressions"
date = 2026-05-24
math = true
tags = ["Neural Networks", "Large Language Model", "Transformer-based model", "similarity", "BERT Language Model", "Small Language Model"]
+++

### Previous

A dual encoder is a neural architecture designed for retrieval tasks, where it encodes a query and a document (or passage) independently into a shared embedding space. The core purpose of the dual encoder is to support efficient semantic similarity comparison using vector-based operations, typically a dot product or cosine similarity.

Let the query be denoted by $q$ and the passage/document be denoted by $p$. The encoder network maps each of these inputs to dense vector embeddings:

$$
\mathbf{q}\_{\text{emb}} = \text{Encoder}\_Q(q) \in \mathbb{R}^d, \quad
\mathbf{p}\_{\text{emb}} = \text{Encoder}\_P(p) \in \mathbb{R}^d
$$

where $d$ is the embedding dimension, often fixed (e.g., $d = 768$).

The relevance score between $q$ and $p$ is computed by a simple similarity function such as the dot product:

$$
\text{sim}(q, p) = \mathbf{q}\_{\text{emb}} \cdot \mathbf{p}\_{\text{emb}}
$$

or optionally, the cosine similarity:

$$
\text{sim}(q, p) = \frac{\mathbf{q}\_{\text{emb}} \cdot \mathbf{p}\_{\text{emb}}}{\|\mathbf{q}\_{\text{emb}}\| \|\mathbf{p}\_{\text{emb}}\|}
$$

The training objective uses in-batch negative sampling and softmax loss, with the formula:

$$
\mathcal{L} = -\log \frac{e^{\text{sim}(q\_i, p\_i^+) / \tau}}{\sum\_{j \in B} e^{\text{sim}(q\_i, p\_j^+) / \tau}}
$$

where:

- $p\_i^+$: the positive passage relevant to $q\_i$
- $\tau$: softmax temperature
- $B$: mini-batch size


{{< related >}}

