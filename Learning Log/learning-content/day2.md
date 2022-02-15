## Day 2 - 15th Feb, 2022


### Two Approaches to NLP

#### Approach 1: Classical View

This is the algorithmic view where we process the text in stages, and we try to resolve ambiguities and challenges at each stage using certain algorithms. In these algorithms, the processing is governed by the rules given by us.

For example, in syntactic analysis stage, a linear sentence data needs to be converted into a tree-like structure. We can create rules using Context-Free Grammar from Automata theory, like 

```
sentence -> noun_phrase + verb_phrase
noun_phrase -> pronoun | proper_noun | det + nominal
nominal -> noun + nominal | noun
verb_phrase -> verb | verb + noun_phrase | verb + noun_phrase + preposition_phrase | verb + preposition_phrase
preposition_phrase -> preposition + noun_phrase
```

The aim of above grammar is to genearte the language viz. English, to create the sentences from the dictionary of words. This dictionary is built from the corpus text. Corpus is the huge amount of text used by the program/us to formulate the rules. 

```
noun -> flight | breeze | morning | tree | ...
verb -> is | prefer | need | want | fly | ...
adjective -> cheapest | non-stop | first | cool | direct | ...
pronoun -> me | I | you | it | ...
determiner -> the | a | this | an | ...
preposition -> from | to | on | near | ...
conjunction -> and | or | but | ...
```

Above-mentioned grammar is a very crude grammar and doesn't really generate all the english sentences. But this gives us general idea about how we go for NLP with the classical approach. 

#### Approach 2: Machine Learning & AI View

In the machine learning view, we don't really provide all the rules to the machine. But instead we let machine train over the corpus data and understand the hidden knowledge & rules of the language by itself. So, the setting of the machine learning problem in the NLP domain is: 

* Goal: _Classification/Clustering_
* Features: _Word positioning, morphology, word labels, ..._
* Training data: _Corpus (annotated/un-annotated)_
* Test data: _Test corpus_
* Accuracy: _Precision, Recall, F-score, MAP, ..._
* Test of Significance: _Moving from small sample space to more general class of sentences_

By annotation, we mean labelling of words in the corpus. Imagine we have a very small corpus of 3 words: "People laugh heartily". Here, we can annotate each word as: 

* people: {Noun, takes no extra suffix for plural, a generic word for group of humans, animate, collective type}
* laugh: {Verb, _ed for past tense, verb of state}
* heartily: {Adverb, adverb of manner}

What do we expect from the ML model after providing annotated corpus? 

**Option 1: A set of rules**

Rule: _If the word to the left of the verb is a noun and has 'animate' feature, then it is likely agent of the action denoted by the verb._

* The child broke the toy. (_child_ is the agent)
* The window broke. (_window_ is not the agent because it is inanimate)

**Option 2: A set of probability values**

We may want to find the relationship between the probability values & we get a set of probability values using which we can form the relationship. Example: 

P(agent | word is to the left of verb and has animate feature) > P(object | word is to the left of verb and has animate feature) > P(instrument | word is to the left of verb and has animate feature) 

<hr/>