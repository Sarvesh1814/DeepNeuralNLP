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

## Code Explanation 

### Data Preparation:

Replace the corpus variable with your text corpus. The corpus should be a list of documents separated by periods.

### TF-IDF Vectorization:

Calculate TF-IDF values for the words in the corpus using the TfidfVectorizer from Scikit-Learn.

### Initialization:

Initialize context sentence vectors (Mc) using TF-IDF values.
Initialize random sentence vectors (Wt and Wc) for center and context sentences.

### Hyperparameters:

Set hyperparameters such as epochs, window_size, and learning_rate according to your requirements.

### Sigmoid Activation Function:

Define the sigmoid activation function.

### Binary Cross-Entropy Loss Function:

Define the binary cross-entropy loss function.

### Training Loop:

1. Train the Word2Vec model with Skip-gram using binary cross-entropy loss.
2. For each epoch:
3. Shuffle the indices of the sentences.
4. Split the data into batches (each containing batch_size sentences).
5. For each sentence in each batch:
   Compute the raw score (z) for the sentence.
   Apply the sigmoid activation function to get the predicted context vector.
   Calculate the loss based on binary cross-entropy between the predicted and true context vectors.
6. Using gradient descent, Update the weight matrices (Wt and Wc).
7. Accumulate the loss for the epoch.
8. Print the total loss for the epoch.
9. If the total loss falls below a threshold, stop training.
