## Day 1 - 14th Feb, 2022

Started learning Natural Language Processing (NLP). 

### Introduction to NLP

#### Areas of AI & their inter-dependencies

The aim of AI in the recent times have been to make the machines as closer to humans as possible. There are many areas of AI and they have inter-dependencies when we consider the entire task of _making a machine behave like a human_ as a whole. We start from the lowermost layer and go all the way up to understand the following dependency graph. 

<img src="../img/areas_of_ai_and_dependencies.jpg" width="400">

<br>

* NLP: NLP is concerned with the computer being able to process human-like languages like English, French, Hindi, Marathi, etc. 

* Vision: In Computer Vision (CV), the computer understands visual scenes and understands what's happening in the surroundings. Based on this info, it can take certain decisions on how to operate in the given scenario. 

* Robotics: In Robotics, there is an embedded software that performs various actions like locomotion, monitoring surroundings, responding to audio signals, picking up supplies, etc.

* Expert Systems: It is concerned with the expert level performance of a software on a specific task. Eg. The task could be diagnosis of a disease & suggest cure if possible. A doctor operates with a large number of rules which he/she has obtained from years of education & practice to do the same task. 

These all human-like systems are fed by blocks in the second layer. 

* Machine Learning: This is a domain where the machine learns the knowledge contained in the data. Eg. In today's internet world, we have a huge amount of text. It is important to learn the data contained in it, so that the machine could understand the text when given the next time. 

* Planning: This area is concerned with making strategies or action sequences that are required for execution of tasks by autonomous robots & unmanned vehicles. Typically a robot/vehicle needs to carry out multiple decisions at the same time. So this area of AI concerns with the automated scheduling of the decisions to carry out the task in the optimal manner. Hence, planning is mostly concerned with robotics & not with NLP. 

First layer blocks: 

* Search: In search, the machine is faced with a number of choices. Search algos try to find out the best possible strategy for the machine. Eg. In NLP, the text goes like "I went to the bank to withdraw some money". Here, "bank" word has two meanings - (a) the financial institute (b) the land alongside the lake or river. Out of these two, which meaning should the computer pick? This decision making process requires search. 

* Logic: Logic is the formal representation of the rules we follow to make the inference. Eg. The knowledge gathered from the text needs to be strutured in a logical form or certain set of rules to derive the meaning from it. Propositional Calculus, Predicate Calculus and some other forms of non-monotonic logic are used in NLP for this. 

* Knowledge-Representation: Machines only understand binary. However, in NLP type of area of AI, we deal with words. The task here is to convert the sentence in the form of numbers such that the numeric data still somehow contains the meaning which the textual data was containing. 

#### Goals of NLP

* Science Goal: Understand the way language operates for machines.
* Engineering Goal: Build the systems that analyse & generate language, thereby reducing the man-machine gap. 

#### History of NLP

It all starts from Turing proposing "The Turing Test". Turing proposed "The Imitation Game" in 1950, to test if the machine is truly intelligent or not. The test is - Person A in one room needs to communicate via keyboard to two responders in two rooms, one containing the Person B and other containing the Machine. Person A will ask questions and if he is unable to identify which room has the Machine via the answers he/she gets, then Machine has successfully imitated a Person & is considered as truly intelligent.   

<img src="../img/turing_test.jpg" width="400">

<br>

In 1966, Joseph Weizenbaum created a program which appeared to pass the Turing test. The program, known as ELIZA, worked by examining a user's typed comments for keywords. If a keyword is found, a rule that transforms the user's comments is applied, and the resulting sentence is returned. If a keyword is not found, ELIZA responds either with a generic riposte or by repeating one of the earlier comments.

You can interact with ELIZA here: http://psych.fullerton.edu/mbirnbaum/psych101/eliza.htm 

John Searle's 1980 paper Minds, Brains, and Programs proposed the "Chinese room" thought experiment and argued that the Turing test could not be used to determine if a machine can think. Searle noted that software (such as ELIZA) could pass the Turing test simply by manipulating symbols of which they had no understanding. Without understanding, they could not be described as "thinking" in the same sense people are. Therefore, Searle concludes, the Turing test cannot prove that a machine can think.

Arguments such as Searle's and others working on the philosophy of mind sparked off a more intense debate about the nature of intelligence, the possibility of intelligent machines and the value of the Turing test that continued through the 1980s and 1990s.

The Loebner Prize provides an annual platform for practical Turing tests with the first competition held in November 1991. It is underwritten by Hugh Loebner. The Cambridge Center for Behavioral Studies in Massachusetts, United States, organised the prizes up to and including the 2003 contest. As Loebner described it, one reason the competition was created is to advance the state of AI research, at least in part, because no one had taken steps to implement the Turing test despite 40 years of discussing it.

The silver (text only) and gold (audio and visual) prizes have never been won. However, the competition has awarded the bronze medal every year for the computer system that, in the judges' opinions, demonstrates the "most human" conversational behaviour among that year's entries. 

Artificial Linguistic Internet Computer Entity (A.L.I.C.E.) has won the bronze award on three occasions in recent times (2000, 2001, 2004). Learning AI Jabberwacky won in 2005 and 2006.

#### Stages of Language Processing

What makes NLP so challenging is the ambiguity. But before deep diving into how to work around ambiguity, we need to understand the stages of language processing. There are in all 7 stages, as mentioned below.

* Phonetics & Phonology
* Morphology
* Lexical Analysis
* Syntactic Analysis
* Semantic Analysis
* Pragmatics
* Discourse

**Phonetics**

This stage is concerned with processing of speech. 

Challenges in this stage are: 

* Homophones: bank (finance term) vs. bank (land alongside river)
* Word Boundary: "aajayenge" in Hindi, can be interpreted in two ways. "aa jayenge" - meaning "will come" vs. "aaj ayenge" - meaning "will come today". "I got a plate" in English, can be interpreted in two ways again: "I got a plate" vs. "I got up late". 
* Disfluency: _ah_, _um_, _ahem_, etc. which a user utters while speaking. These words have no meaning, it just allows user to gain time to organize his thoughts. 

**Morphology**

This stage is concerned with word formation rules from the root words. 

Challenges in this stage are: 

Using the root word, we can create other word in different contexts. 

* Singular-Plural conversion: Eg. boy -> boys
* Male-Female conversion: Eg. Tzar -> Tzarina
* Tense conversion: Eg. stretch -> stretched
* Modality conversion: Eg. "Khaana" (food/noun) -> "Khaiye" (requesting to eat food/verb)

We need to work with all the different forms of the same root word. There are morphologically rich languages like Dravidian (South-Indian languages), Hungarian, Turkish, etc. and morphologically poor languages like Chinese, English, etc. Languages with rich morphology have an advantage of easier processing at higher levels & thus, of our particular interest.

**Lexical Analysis**

