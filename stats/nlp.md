##Natural Language Processing

####TDIDF

TF-IDF the number of a times a word appears in a document (aka 'corpus') is considered in the model

TF = term frequency; considers raw frequency of a term in a document

IDF:  an inverse document frequency factor is incorporated which diminishes the weight of terms that occur very frequently in the document set and increases the weight of terms that occur rarely.  Example:  word 'the'

LDA Source
https://www.quora.com/What-is-a-good-explanation-of-Latent-Dirichlet-Allocation

LDA:  Latent Dirichlet allocation is a way of automatically discovering topics that are contained in a document. 
- common method of topic modeling
-

(note: LDA is a bag-of-words model)
bag-of-words: 
text (such as a sentence or a document) is represented as the bag (multiset) of its words, disregarding grammar and even word order but keeping multiplicity.

The Latent part of LDA comes into play because in  statistics, a variable we have to infer rather than directly observing  is called a "latent variable". We're only directly observing the words  and not the topics, so the topics themselves are latent variables (along  with the distributions themselves).
