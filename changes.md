# CHANGES

These are the changes in the different chapters (disregarding misspellings, grammatical errors and incomplete sentences).

## General

* Depth of numbering increased to chapter + 2 levels of sections
* Table of content follows this. I based this decision on that if someone sees a reference to 3.2.1 he/she might use the TOC to see what it's about.
* [h] are removed from figures, tables and algorithms.
* Question: In the experiments and discussion -- Should I give them name, or is "experiment 1" sufficient?

## Introduction

* Added picture of active learning model components (Active Learning - Query Selection --> only Sampling Strategy). Some dotted lines were drawn between the things that the sampling strategy has access to.
* Clarified what I meant by using the underlying structure of the data to select points. I just extended the sentence to include "by applying techniques such as clustering".
* Moved some of the background to the introductory part of the introduction, and them some more specifics to the aim. I think this shows the reasoning behind the research questions in a better way. Some background information on Sectra that I mostly used to fill out the background a bit more was discarded.
* The research questions are restructured according to our discussion. The alternatives that will be evaluated are brought up in a paragraph before the listing of the questions, with a forward pointer to discussion for the motivation behind the choices.
* The effects of the delimitations were slightly elaborated on.
* The structure of the report section now includes reference to each chapter by number.

## Theory

I am not completely sure if this provide enough structure, especially for the unsupervised techniques. 
Any suggestions on how to further clarify this? Maybe split it up into several sections?

* Reorganized according to our discussion. The structure is now:
    1. Text Classification
    2. Active Learning
    3. Other techniques ()
* A paragraph on representing texts as bag of words was added before text classification. I thought it was logical to represent it in some way before talking about the models, but maybe it should be moved? Or does it need to be in the theory at all?
* Added further explanation of the mathematical definition of the version space. Removed the mathematical definition of the hypothesis space, since it did not really provide additional information and isn't needed for subsequent discussion. It was used by one paper in order to restrict another discussion to case where ||w|| = 1, which is not needed here (and most papers does not include the definition).
* Added an analogy to binary search to explain why the version space should (optimally) be cut in half each iteration. 

## Data
* Pulled together different parts from the method and results, and fixing the issues in that text.

## Experiments
* Pulled together different parts from the method and results, and fixing the issues in that text.
* The framework/implementation parts were added to the end of this chapter. Some of the libraries there are mainly used in the data chapter, but it's a rather small section so I thought that it might be okay to leave it where it is.

## Discussion
* Organized according to experiments
* Moved related work here, not sure how well it fits?