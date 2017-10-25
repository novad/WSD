# Word Sense Disambiguation with NLTK

>*note that this repo is a work in progress*

In the field of Natural Language Processing, Word Sense Disambiguation (WSD) is the task of finding the correct sense of a word token given its context, this is a crucial part in semantic analysis, analyzing dialogue, question answering, machine translation, and many other applications.
To illustrate word ambiguity let's see an example from the Senseval corpus:
> ”Abbie Hoffman in this case is to be **played** by Hollywood actor Paul LieberAbbie Hoffman[...]”

> ”At noontime, remembering what the teacher had said about maybe **playing** with the kids[...]”

In these two sentences, verb **play** has different senses. First one refers to the sense: *"play a role or part"*, and the second one to: *"be at play; be engaged in playful activity; amuse oneself in a way characteristic of children"* (taken from [WordNet](http://wordnetweb.princeton.edu/perl/webwn?s=play&sub=Search+WordNet&o2=&o0=1&o8=1&o1=1&o7=&o5=&o9=&o6=&o3=&o4=&h=) )

As Jurafsy and Martin [1] put it, the intuition behind this task is that similar meanings occur in similar contexts, either in terms of corpora (the neighboring words, syntactic structures), or in terms of dictionaries and thesauruses (that is similar definitions, or close in a thesaurus hierarchy).

WSD tasks can be distinguished into two variants:
1. **Lexical tasks**: Given a set of labeled target words, and a set of sentences examples associated with each target word, we can train a classifier using these labeled examples. We use supervised learning.
2. **All-words tasks**: Given a set of texts and a lexicon with an inventory of senses for each entry, disambiguate all content words in the text. We need to use semi-supervised or unseupervised learning approaches.

# Organization of the repo
The repo is divided into folders according to the used approach.
Implementation is done using Python (actually Jupyter notebooks) and the Natural Language Toolkit ([NLTK](http://www.nltk.org/)).

## Supervised Approach. Naïve Bayes Classifier
In the `SupervisedWSD` folder we will find file `NaiveBayes.ipynb` file with the code for this approach. This is a **lexical** task.

The first approach uses Naïve Bayes classification. From a Machine Learning perspective WSD involves a classification task, that is classify a word as belonging to a class representing its sense.
When a labeled corpus is available containing the correct word senses, we perform WSD using a supervised ML approach, that is extracting useful features, and training a classifier

We use the Senseval 2 corpus formatted by Ted Pedersen (available at: <http://www.d.umn.edu/~tpederse/data.html>)
This corpus also provides some instances with POS tags. (If you're not familiar with POS tagging take a look at [chapter 5 from the NLTK book ] (http://www.nltk.org/book/ch05.html))
If you haven't downloaded the NLTK corpus, you can do it by running:
```python
import nltk
nltk.download()
```
For information about check <http://www.nltk.org/data.html>.
We'll see how accuracy changes when using POS-tagged and a non POS-tagged data.


## Thesaurus-based approach. Lesk Algorithm
*To be added later*

## Semi-supervised approach. Bootstraping.
*Work in progress*


Might add in the future some unsupervised learning approaches to WSD.


---

This repo was originally developed for the Natural Language Processing course at Politecnico di Milano.

## References
1. S. Bird, E. Klein, and E. Loper, "*Natural Language Processing with Python*". Available at: <http://www.nltk.org/book/>
2. Jurafsky, D. Martin, J. (2008) ”*Speech and Language Processing: An Introduction to natural language processing*, computational linguistics, and speech recognition”. Second Edition. Prentice Hall

Jurafshy and Martin are working on a new version of the book *"Speech and Language Processing"*, new chapters are being added with new and interesting topics. Updates and a draft of the book can be found [here] (https://web.stanford.edu/~jurafsky/slp3/).
