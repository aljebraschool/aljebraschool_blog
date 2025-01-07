---
title: "What is Attention in Large Language Model"
datePublished: Tue Jan 07 2025 11:26:10 GMT+0000 (Coordinated Universal Time)
cuid: cm5mdxedo000o09jsgldu9y78
slug: what-is-attention-in-large-language-model
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1736249085380/22ccf5e4-be71-4f6b-ac27-5a64bc65a1ee.jpeg
tags: llm, embedding, attention-mechanism

---

## Introduction

---

Human language is intricate and multifaceted, with its complexity arising from two fundamental elements: semantics and context. Semantics refers to the literal, dictionary meaning of words, while context shapes how those words take on different interpretations depending on their usage in sentences. For example, the word “bank” can signify either a financial institution or the side of a river. The distinction depends on the context in which the word appears.

However, computers process information differently. Unlike humans, they don't naturally grasp the nuances of language. Computers represent words as numerical values, often treating the same word identically regardless of its contextual meaning. This can lead to ambiguity and misinterpretation in language processing tasks.

So, how do computers learn to understand and distinguish words based on their context? This is where “Attention” comes into play. Introduced by Google in a groundbreaking 2017 [paper](https://arxiv.org/abs/1706.03762), the Attention mechanism enables computers to weigh the importance of different words within a sentence, allowing them to derive meaning in a way that mimics human comprehension. By incorporating Attention, machines can better capture the subtle and dynamic nature of language, significantly improving tasks like translation, summarization, and sentiment analysis.

# Attention Mechanism intuition

To gain a clearer understanding of the Attention mechanism, let's examine these examples:

1. "The bank of the river" – Sentence 1
    
2. "Money in the bank" – Sentence 2
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1736249723840/fc884171-9b54-4863-93a8-182994bd253b.png align="center")

How does a computer determine that "bank" in the first sentence refers to the side of a river, while in the second sentence it means a financial institution? To answer this, let's consider how humans make these distinctions. We read the entire sentence and examine the surrounding words to identify the context. In these examples, "river" and "money" provide the necessary clues. Computers achieve similar contextual understanding through the use of word embeddings.

To illustrate this more clearly, let's convert Sentence 1 into an equation by emphasizing the key features and disregarding less important words: 0.9 x bank1 + 0.1 x river. Similarly, for Sentence 2, we have 0.8 x bank2 + 0.2 x money. We use bank1 and bank2 to differentiate between the meanings of "bank" in these sentences.

As explained in our previous blog post on word embeddings, each word is represented by a vector of numbers. Let's assign the following vectors:

* River: \[0, 5\]
    
* Money: \[8, 0\]
    
* Bank: \[6, 6\]
    

Now, let's calculate the embeddings for the word "bank" in each sentence using the equations provided.

For Sentence 1, with the equation 0.9 x bank1 + 0.1 x river, we calculate the embedding as follows: 0.9 x \[6, 6\] + 0.1 x \[0, 5\] = \[5.4, 5.9\].

For Sentence 2, with the equation 0.8 x bank2 + 0.2 x money, the embedding is calculated as: 0.8 x \[6, 6\] + 0.2 x \[8, 0\] = \[6.4, 4.8\].

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1736245291693/de622339-acbb-45dd-98a0-ba6b0ec19022.png align="center")

When plotted on a Cartesian plane, bank1 appears closer to river, while bank2 is nearer to money. This differentiation is achieved through embeddings.

# How to choose word for context

Why were the words "money" and "river" chosen instead of others like "and" or "of" to determine the context of "bank"? For humans, this is intuitive due to our language familiarity. However, computers rely on two mechanisms: Similarity and Multi-head attention.

In the similarity mechanism, the computer considers all words as context, including irrelevant ones like "of," and compares their vectors with that of "bank." A good embedding results in a high similarity score for related words (close to 1) and a low score for unrelated ones (close to zero), helping identify the most relevant contextual word.

This technique forms the foundation of self-attention. Multi-head Attention takes this further by processing multiple embeddings at once, enabling the system to capture diverse aspects of word meaning simultaneously, leading to a richer understanding of language.

# **Conclusion**

The Attention mechanism represents a groundbreaking advancement in natural language processing, enabling machines to interpret context much like humans. By allowing computers to focus on the most relevant parts of a sentence, attention not only resolves ambiguities but also enhances the overall performance of language models in tasks like translation, summarization, and sentiment analysis. As the field of AI continues to evolve, the refinement of attention-based models will further bridge the gap between human and machine understanding, driving innovation across countless applications.

# References

Cohere, "What Is Attention in Language Models?," LLM University. \[Online\]. Available: [https://cohere.com/llmu/what-is-attention-in-language-models](https://cohere.com/llmu/what-is-attention-in-language-models)