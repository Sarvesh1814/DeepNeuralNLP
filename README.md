# Assignment 1: Train Word2Vec on peS2o Dataset (AllenNLP)

## Introduction

This assignment focuses on training a Word2Vec-based model on the peS2o dataset with specific requirements and preprocessing steps. The goal is to embed sentences from computer science research papers and create a context matrix using tf-idf-based vector modeling.

## Requirements

1. **Domain Selection**: We will collect research papers only from the computer science domain.

2. **Data Split**: We will use a random training dataset consisting of 3000 documents, and a test dataset containing 1000 documents.

3. **Context Unit**: Instead of embedding individual words, we will embed sentences. Each row vector in the input context matrix will represent a sentence.

4. **Preprocessing**:
   - Remove stopwords: Common words like "and," "the," "in," etc., which do not carry much meaning, will be removed.
   - Remove URLs: Any URLs present in the text should be removed.
   - Remove bullets: Bullet points or any non-textual information should be removed.
   - Remove apostrophes: Apostrophes should be handled, e.g., "it's" becomes "its."
   - Handle hyphens: Hyphenated words should be split or joined as needed.
   - Remove enumerations: Enumerations like numbered lists should be removed.
   - Numerical-to-text conversion: Convert numerical values to their text representation, e.g., "10" becomes "ten."
   - Remove punctuations: Remove any punctuation marks.

5. **Context Matrix Initialization**: Initialize the context matrix using tf-idf (Term Frequency-Inverse Document Frequency) based vector modeling. This means that each sentence will be represented as a vector considering the importance of words in the entire dataset.

## Implementation

Here is an outline of how to implement the above requirements:

1. **Data Collection**:
   - Collect research papers from the computer science domain.

2. **Data Split**:
   - Randomly split the dataset into a training set with 3000 documents and a test set with 1000 documents.

3. **Preprocessing**:
   - Implement the preprocessing steps mentioned above using appropriate libraries and techniques. Libraries like NLTK, spaCy, or AllenNLP can be useful for this task.

4. **Word2Vec Model Training**:
   - Use AllenNLP or a similar library to train a Word2Vec model.
   - Input for the model should be the preprocessed sentences.

5. **Context Matrix Initialization**:
   - Compute tf-idf scores for words in the entire dataset.
   - For each sentence, create a vector representation based on the tf-idf scores of the words it contains.


