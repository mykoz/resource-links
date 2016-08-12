##NER paper notes

####CRF (conditional random field)
A CRF is a probabilistic model which, in our task, predicts the label of each token ("+" or "-"), given both information endogenous to the token (e.g. 'token is a number', 'token is the word *bridges*') as well as information exogenous to the token (e.g. 'token is preceded by the word *closing*')
