7/27/16  

shared google drive  

###Data
data to use:  data/all.iob  
structure:  **token**, **class**  
we can add classes:  url, mention, emoji  
capitalization:  preserve.  it is important for named entities  
mark beginning / end of tweet with a space  
make a list of errors:  London O should be London O-geoloc

```
Example:  4-gram, phase: "Vote for Trump"
Vote  O
for   O
Trump B-person

---
Vote O
otef O
tefo O
efor O
forT O , B-person
orTr O
rTru O
Trum O
rump O

figure out when we want to assign B-person
```

1)  
https://archive.org/  
old Twitter data 2011  
general model for character sequence; see if there are other langs  

2)  
Embeddings:  word2vec --> papers

3)  
####IOB - Inside, Outside, Beginning 
Weiss et al 2005  MEMMs  
The IOB format (short for Inside, Outside, Beginning) is a common tagging format for tagging tokens in a chunking task in computational linguistics (ex. Named Entity Recognition).[1] The B- prefix before a tag indicates that the tag is the beginning of a chunk, and an I- prefix before a tag indicates that the tag is inside a chunk. The B- tag is used only when a tag is followed by a tag of the same type without O tokens between them. An O tag indicates that a token belongs to no chunk.

Another similar format which is widely used is IOB2 format, which is the same as the IOB format with the difference that the B- tag is used in the beginning of every chunk (i.e. all chunks start with the B- tag).  

####NER - Named Entity Recognizer  

####CRF - Conditional Random Field
Conditional random fields (CRFs) are a class of statistical modelling method often applied in pattern recognition and machine learning, where they are used for structured prediction. Whereas an ordinary classifier predicts a label for a single sample without regard to "neighboring" samples, a CRF can take context into account; e.g., the linear chain CRF popular in natural language processing predicts sequences of labels for sequences of input samples.  


character based systems  
non-linear CRFs  

3.  retrain CRFs & produce results  

MEMM  

####Action:  convert training data to character format 
can put in a public repo  

####Action:  twitter NLP - what is being done out there
nvert training data to character format 

####Action:  read papers

