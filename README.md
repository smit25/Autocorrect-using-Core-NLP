# Autocorrect-using-Core-NLP

## Introduction
I've implemented custom spellcheck/autocorrect using the core concepts of probabilistic models without relying on NLP libraries like nltk or spacy. 

## Dataset
Google n-grams being a very huge dataset and the others being paid, I decided to use stories of Sherlock Holmes( which I'm currently reading as well) as my dataset for the language model. The code can be extrapolated to bigger datasets.

## Salient Features 
  *The probability of a sentence is determined by interpolation of trigram, bigram, and unigram, the coefficients of which have been trained and determined by Adadelta/ Adam optimizer.
   *A suitable replacement for an input word that does not exist in the dictionary(enchant) is generated by using the Levenshtein Edit Distance algorithm.
  *Zeroes or unknown words in the input have been taken care of by implementing Stupid Backoff and Laplacian Smoothing along with inclusion of'<unk>' at suitable places in the dataset.
  *Proper Nouns are given separate status and are bypassed from procuring autocorrect recommendations.
  * The assumptions of the model have been mentioned in the code attached
  
 ## Running Tests 
 A flask script has been attached towards the end to successfully implement the algorithm.
 To run the model, run the code or type the command:
 ```bash
 python {scriptname}
 ```
 or
 ```bash
 flask run
 ```
 
  
## Future Modifications
To add: Adding a bais probability to words in the input which exist in the dictionary yet have a lesser probability than another similar more frequently used word.(eg: deceive, receive)
