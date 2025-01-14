---
title: "The Mechanics of Transformer Models: What They Are and How They Work"
datePublished: Tue Jan 14 2025 14:21:30 GMT+0000 (Coordinated Universal Time)
cuid: cm5wk9tx1000f0ame2kpm3msm
slug: the-mechanics-of-transformer-models-what-they-are-and-how-they-work
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1736850076476/402ea06b-601e-40ee-89bd-9b0bd4e9cdaa.png
tags: nlp, gpt-3, transformers, bert, attention-mechanism

---

## Introduction

---

The smartphone era has brought us devices that not only connect us but also assist in generating ideas, such as writing. Early smartphones introduced basic text completion tools that suggested words as we typed on virtual keyboards. While these tools were helpful for suggesting individual words, they often struggled with producing coherent sentences when used to compose longer messages. For example, if you began a message with "How are," the suggested completions might include "you" or "your." However, as you continued selecting suggestions to form a sentence, the result often lacked clarity and meaning. This limitation arose because the underlying models generated suggestions without fully understanding the context of the text.

In 2017, Google transformed this landscape with the introduction of transformer models, as described in their seminal paper, "Attention is All You Need." Transformers are designed to comprehend the context of entire sentences—or even larger portions of text—allowing them to generate more meaningful, context-aware suggestions one step at a time. While the transformer architecture consists of both an Encoder (used to understand context, as seen in models like BERT) and a Decoder (specialized in text generation, as seen in GPT models), this article will focus on a simplified version of the transformer model to make its mechanics more accessible.

# Transformer Architecture

The transformer architecture can be broken down into five key components:

1. **Tokenization**
    
2. **Embedding**
    
3. **Positional Encoding**
    
4. **Transformer Blocks** (a series of them)
    
5. **Softmax Activation Function Layer**
    

![The architecture of a transformer model](https://cohere.com/_next/image?url=https%3A%2F%2Fcohere-ai.ghost.io%2Fcontent%2Fimages%2F2024%2F07%2Ftransformer-architecture.png&w=3840&q=75 align="left")

## Tokenization

Tokenization is a preprocessing technique used to transform human-readable text into a format that computers can process. It involves breaking down text into smaller units, such as sentences or words, making the data easier for models to analyze and process.

Tokenization can be applied at different levels:

* **Sentence Tokenization**: Splitting a paragraph or corpus into individual sentences.
    
* **Word Tokenization**: Further breaking down each sentence into individual words.
    

For example, consider the following paragraph (corpus):

*"The era of smartphones has revolutionized how we generate ideas. Writing is now assisted by intelligent tools that help complete our sentences."*

* **Sentence Tokenization** would split this into:
    
    1. *"The era of smartphones has revolutionized how we generate ideas."*
        
    2. *"Writing is now assisted by intelligent tools that help complete our sentences."*
        
* **Word Tokenization** would break the first sentence into:
    
    * *"The"*, *"era"*, *"of"*, *"smartphones"*, *"has"*, *"revolutionized"*, *"how"*, *"we"*, *"generate"*, *"ideas."*
        

This structured representation of text is crucial for feeding data into the transformer model.

```python
corpus = """
    Hello my name is Ridwan Ibidunni. I am a graduate of mathematics with a keen interest in developing AI applications
    to solve problems in our environments. I love coding and teaching people how to code.
"""
```

To tokenize this group of sentences, we have to use the `nltk` library in python, see the implementation

```python
import nltk # import nltk
# Download the 'punkt_tab' data package
nltk.download('punkt_tab')

#import then method needed to tokenize sentence from nltk
from nltk import sent_tokenize
#apply this method on the corpus 
document = sent_tokenize(corpus)

#view the tokenized sentence
for item in document:
    print(item)

""" ### output ###
Hello my name is Ridwan Ibidunni.
I am a graduate of mathematics with a keen interest in developing AI applications
    to solve problems in our environments.
I love coding and teaching people how to code.
"""
```

This implements sentence tokenization

Now let’s implement word tokenization for each sentence.

```python
#import word tokenization library from nltk
from nltk import word_tokenize

#convert paragraph to word by splitting each into separate word
corpus_tokenized_word = word_tokenize(corpus)

corpus_tokenized_word 

""" visualize some of the output 
['Hello',
 'my',
 'name',
 'is',
 'Ridwan',
 'Ibidunni',
 '.',
 'I',
 'am',
 'a',
 'graduate',
 'of',
.....
]

"""
```

This process breaks down each sentence into individual words. It is the first step performed by a Transformer model when you provide it with a block of text or ask it a question like *"write me a story."* By tokenizing, the model ensures it can process the input effectively for further stages.

## Embedding

After tokenization, the next step in the Transformer model is the Embedding layer. This layer translates human language (e.g., English or any other spoken language) into a numerical format that a computer can process. For a deeper understanding of embeddings, you can refer to our [previous writings](https://aljebraschool.hashnode.dev/understanding-context-in-ai-the-impact-of-sentence-embeddings-explained), but here’s a quick summary:

Embedding transforms tokenized words into numerical representations in a vector space. There are different methods to achieve this, including:

1. **One-Hot Encoding**:  
    Each word is represented as a binary vector where the position of the word in the vocabulary is marked with a 1, and all other positions are marked with 0. While straightforward, this method often creates large sparse matrices (with many zeros), which can make the model inefficient and prone to overfitting.
    
2. **Bag of Words (BoW)**:  
    This technique is more practical for text processing. It treats a sentence as a "bag" containing all its words, disregarding the order in which they appear. The primary focus is on the frequency of each word in the bag, which becomes the value assigned to each word. Each unique word (or vocabulary term) forms a feature, and its frequency determines its corresponding value in the feature set.
    
    ```python
    # Step 1: Tokenize sentences and build a vocabulary
    from sklearn.feature_extraction.text import CountVectorizer
    
    # Sample corpus
    corpus = [
        "Machine learning is fun",
        "Learning machine learning is interesting",
        "Machine learning can solve many problems"
    ]
    
    # Initialize CountVectorizer
    vectorizer = CountVectorizer()
    
    # Step 2: Fit and transform the corpus
    bow_matrix = vectorizer.fit_transform(corpus)
    
    # Step 3: Extract the vocabulary and the matrix
    vocabulary = vectorizer.get_feature_names_out()
    bow_array = bow_matrix.toarray()
    
    # Display results
    print("Vocabulary:")
    print(vocabulary)
    
    """ Output ###
    Vocabulary:
    ['can' 'fun' 'interesting' 'is' 'learning' 'machine' 'many' 'problems'
     'solve']
    """
    
    print("\nBag of Words Matrix:")
    print(bow_array)
    
    """ Output
    Bag of Words Matrix:
    [[0 1 0 1 1 1 0 0 0]
     [0 0 1 1 2 1 0 0 0]
     [1 0 0 0 1 1 1 1 1]]
    """
    ```
    
3. **N-Gram**
    
    N-Gram is a technique used to build a vocabulary of consecutive words or text fragments when constructing a model. These fragments can vary in size:
    
    * **Unigram**: A single word.
        
    * **Bigram**: Pairs of consecutive words.
        
    * **Trigram**: Triplets of consecutive words.
        
    
    N-Grams capture word sequences, allowing models to better understand context and dependencies between words.
    
    ```python
    from sklearn.feature_extraction.text import CountVectorizer
    
    # Sample text
    corpus = [
        "Machine learning is fun",
        "Learning machine learning is interesting",
        "Machine learning can solve many problems"
    ]
    
    # Create a CountVectorizer with n-gram range
    vectorizer = CountVectorizer(ngram_range=(2, 2))  # Bigram example
    ngram_matrix = vectorizer.fit_transform(corpus)
    
    # Get the feature names (n-grams) and the resulting matrix
    ngrams = vectorizer.get_feature_names_out()
    matrix = ngram_matrix.toarray()
    
    # Display results
    print("N-grams:")
    print(ngrams)
    
    """ Output
    N-grams:
    ['can solve' 'is fun' 'is interesting' 'learning can' 'learning is'
     'learning machine' 'machine learning' 'many problems' 'solve many']
    """
    
    print("\nN-gram Matrix:")
    print(matrix)
    
    """ Output
    N-gram Matrix:
    [[0 1 0 0 1 0 1 0 0]
     [0 0 1 0 1 1 1 0 0]
     [1 0 0 1 0 0 1 1 1]]
    
    """
    ```
    
4. **Term Frequency-Inverse Document Frequency (TF-IDF)** is a statistical approach for measuring the importance of a word within a document (sentence) relative to an entire collection of documents (corpus or paragraph).  
    Among the techniques mentioned, TF-IDF is highly effective in converting text to numerical representations for machine learning tasks. However, it also comes with limitations, such as not capturing word order or deeper semantic meanings.
    
    ```python
    from sklearn.feature_extraction.text import TfidfVectorizer
    
    # Sample corpus
    corpus = [
        "Machine learning is fun and exciting",
        "Learning machine learning is interesting",
        "Machine learning can solve many real-world problems"
    ]
    
    # Initialize TfidfVectorizer
    vectorizer = TfidfVectorizer()
    
    # Compute TF-IDF matrix
    tfidf_matrix = vectorizer.fit_transform(corpus)
    
    # Get feature names (terms) and their TF-IDF scores
    terms = vectorizer.get_feature_names_out()
    matrix = tfidf_matrix.toarray()
    
    # Display results
    print("Feature Names (Terms):")
    print(terms)
    
    """
    Feature Names (Terms):
    ['and' 'can' 'exciting' 'fun' 'interesting' 'is' 'learning' 'machine'
     'many' 'problems' 'real' 'solve' 'world']
    """
    
    print("\nTF-IDF Matrix:")
    print(matrix)
    
    """" Output
    TF-IDF Matrix:
    [[0.48359121 0.         0.48359121 0.48359121 0.         0.36778358
      0.28561676 0.28561676 0.         0.         0.         0.
      0.        ]
     [0.         0.         0.         0.         0.54861178 0.4172334
      0.64803791 0.32401895 0.         0.         0.         0.
      0.        ]
     [0.         0.38640134 0.         0.         0.         0.
      0.22821485 0.22821485 0.38640134 0.38640134 0.38640134 0.38640134
      0.38640134]]
    """
    ```
    
5. **Word2Vec** is an advanced word embedding technique that represents words in a continuous vector space. It captures both semantic and syntactic relationships between words, making it a powerful tool for text analysis.  
    Unlike simpler methods, Word2Vec is pre-trained on large datasets, where each word is mapped to a numeric vector. When provided with a word, the model identifies its vector and compares it to other word vectors using [**cosine similarity**](https://aljebraschool.hashnode.dev/evaluating-sentence-similarity-step-by-step-guide).
    
    There are two key training approaches for Word2Vec:
    
    1. **CBOW (Continuous Bag of Words)**: Predicts a word based on its surrounding context (neighboring words).
        
    2. **Skip-gram**: Predicts surrounding words based on a given target word.
        
    
    Here’s an example of how to implement Word2Vec using Google’s `gensim` library.
    
6. ```python
     import gensim 
     from gensim.models import Word2Vec, keyedvectors
     import gensim.downloader as api
     
     #note this is very large model
     model = api.load('word2vec-google-news-300')
     
     #get word similar to 'king'
     model['king']
     
     #the most similar word to vehicle
     model.most_similar(['vehicle'])
     
     #check similarity level of words
     model.similarity('flaggerbasted', 'surprised')
     
     #compute this to find the most similar word
     vec = model['king'] - model['boy'] + model['queen']
     
     #most similar word to the word compute above
     model.most_similar([vec])
    ```
    
    Word2Vec is one of the most widely used techniques for creating embeddings for large-scale language models. It utilizes neural networks and supervised learning techniques, leveraging massive datasets to produce high-quality word representations.
    

## Positional Encoding

When tokenized words are converted into numerical vectors, they need to be combined back together for the computer to process them effectively. One way to combine vectors is by adding them component-wise. For example, if **vector\_1 = \[2, 3\]** and **vector\_2 = \[4, 5\]**, their sum would be **\[6, 8\]**. However, this approach assumes vector addition is commutative—meaning the order of addition doesn’t matter.

In language, though, word order is crucial. Sentences like *“I’m not sad, I’m happy”* and *“I’m not happy, I’m sad”* contain the same words, but their meaning changes entirely based on the order. Without a mechanism to preserve word order, these sentences would produce identical vectors, which is incorrect.

**Positional encoding** solves this problem by encoding the position of each word in a sentence into its corresponding vector. This ensures that sentences with the same words but in a different order produce distinct representations, preserving the unique meaning of each sequence.

## Transformer Block

The **Transformer block** is the core component responsible for predicting the next word in a sequence, based on the input it receives from the positional encoding layer.

Each Transformer block consists of two main components:

1. **Feedforward Layer**: Predicts the next word in the sequence.
    
2. **Attention Layer**: Maintains the context of the sentence by analyzing relationships between words.
    

These two components work together to form the **Transformer block**, enabling the model to process language with both accuracy and contextual understanding. As shown in the diagram, the Attention layer is applied at every stage of the feedforward layer, ensuring that word predictions are contextually informed.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1736847332833/2f477c76-c885-4cf5-b356-d4b6c25cbb37.png align="center")

## Softmax Activation Layer

The final layer in the Transformer architecture is the **Softmax activation layer**. Predictions from the Transformer block (comprising the Attention and Feedforward components) are passed through this layer.

The Softmax layer converts these predictions into probabilities, producing values between **0 and 1** for each possible next word. The word with the highest probability is selected as the next word in the sequence, enabling the model to generate coherent and contextually appropriate text.

# **Conclusion**

Transformer models have revolutionized the way machines process and generate human language. By combining key components like tokenization, embedding, positional encoding, Transformer blocks, and the Softmax activation layer, these models achieve remarkable accuracy in understanding context and generating meaningful text.

Their ability to consider the entire context of a sentence, thanks to the Attention mechanism, sets them apart from previous models that struggled with understanding long-term dependencies. Today, Transformers are the backbone of many cutting-edge technologies, from language translation to conversational AI.

As we continue to innovate in AI, the mechanics of Transformer models will remain pivotal in driving advancements in natural language processing, making them an essential tool for developers and researchers alike.

# **References**

Cohere, "What Are Transformer Models and How Do They Work?," LLM University. \[Online\]. Available: [https://cohere.com/llmu/what-are-transformer-models](https://cohere.com/llmu/what-are-transformer-models)

Vaswani et al., "Attention is All You Need," arXiv. \[Online\]. Available: [https://arxiv.org/abs/1706.03762](https://arxiv.org/abs/1706.03762).