# Embedding-LJST
## Baselines
- LDA (Sklearn)
- BTM http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.402.4032&rep=rep1&type=pdf
- JST https://hal.archives-ouvertes.fr/hal-01762995/document
- ETM (MRF-LDA) https://arxiv.org/pdf/1609.08496.pdf
- SLDA https://papers.nips.cc/paper/3328-supervised-topic-models.pdf

## Methodology
We intend to make use of the similar words based on the embeddings of language models to learn the latent factors better. This helps to put the co-related words into same topic. We add a sentiment layer on top for directed learning.

- Added sentiment layer on top of the LDA.
- Making use of Markov Random Field to learn latent factors better.
- Edges are connections across words to which we will share the latent factors
- Building both Unigram and Bigram model (skipgram) for the following two models.
- We use BERT/XLNet for the embeddings.

#### Model 1:
- Making use of bert Trained models to give out the embeddings which inturn helps to compute the cosine similarity.
- We make use of the cosine similarity to form the edges between the words in a document.
- The edges are formed locally among documents and not globally.

#### Model 2:
- Training Bert/XLNet
- Using attention values from bert, xlnet to find the closely related word which is suitable for the next word prediction
- Witha a particular threshold, taking those values as the edges.


## Datasets Used:
1. https://s3.amazonaws.com/amazon-reviews-pds/readme.html
2. Optum Internal Dataset.

## Results
https://docs.google.com/spreadsheets/d/1QAODYkm5_Y7Pmn0GsQS8J0mmrBQ-Z4Eki7AKCakICc4/edit?usp=sharing
