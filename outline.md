# Thesis Outline

## Introduction

### Problem motivation 

* Introduce the problem
    - The world's population is growing --> take advantage of the text data 
    - Information pertaining to a diagnosis of a patient is often in the form of written medical reports.
    - Utmost importance to ensure the quality of diagnosis and minimize the risk of missing some critical piece of information
    - Automated systems -> Increase efficiency and reassurance

* Quality Assurance
    - Give them reassurance in the quality of their decisions
    - Extra confidence that their diagnosis is correct
    - Utilizing this information can be vital to ensure the quality and speed of health care
    - Study past cases with similar features as a current one
    - Comparing -> doctors can check if they have obtained an abnormal result.
    - This comparison will result in an extra quality assurance in the diagnostic ﬂow.

* Machine Learning
    - Predicting labels + retrieving similar documents by machine learning techniques
    - Machine Learning is a field within computer science where systems use a model that has been trained on an already labeled set of data.
    - Supervised vs Unsupervised
    - This model can then be used to predict outputs given some input, even if that input was not a part of the dataset that trained the initial model.
    - In order to compare a report to those of past cases, some past cases have to be labeled
    - Obtain labeled set of data before training models - cumbersome.

* Obtaining data
    - Text data is often widely available -> it's often easy to come buy, but not labeled.
    - Obtaining high quality data is important to use in machine learning systems, both in health care and other areas.
    - Time for labelling reports -- clinicians times are expensive
    - They can spend more time doing what they do best

* Active Learning
    - Semi-supervised
    - Used when plenty of data, but labelling is more costly.
    - Interactively query for labels
    - By selecting labels -> usually require fewer samples

* The primary dataset of documents that will be used comes from Sectra AB. 
* They have an ongoing research project in which doctors have been manually labeling data. 

* Binary classification, multi-class classification and multi-label
    - Binary classification -> Assign one of two classes
    - Multi-class classification -> Assign one of K classes
    - Multi-label classification -> Assign a subset of K classes
    - For active learning:
        - Multi label is harder
        - If you only need to assign one label - you can stop when it's found
        - Multi label you have to identify all -> more important with active learning to reduce the number of samples

### Motivation

* Sectra has a project with Region Skåne
* They have been manually labeling data
* Primary motivation is to make it easier and more efficient to label data for use in machine learning systems
* This would allow doctors to participate in more research projects and thereby help Sectra's products get better

### Aim

The purpose of this thesis project is to build a system to label report data for Sectra. The system will use Topic Models, document clustering and active learning to classify reports in a structured way.

### Research Questions

- Filter out reports that aren't of any use in a machine learning system? i.e. cancellations etc
- How much better can we make the system compared to random sampling?
- Can we enhance the system by taking advantage of the structure of the data - clustering, density etc

### Delimitations

* Data from only one data source (although evaluated on others)

### Structure of the report

Just go through the chapters

## Theory

### Text Processing

* Representing text (bag of words, tf-idf)
* Feature selection - stopword removal, stemming

#### Topic Models

* LDA is generally more used. Not as susceptible to overfitting -- clustering paper in mining data 
* Explain collapsed gibbs

### Text Clustering

* Cluster analysis is usually defined as finding groups in a given dataset. The members of these groups are determined to be similar by a similarity measure (cite clustering mining text data and finding groups in data: an introduction to cluster analysis)
* Since data is sparse, but with high dimensionality (order of 10^5, entire vocabulary). Some naive clustering methods may not work well.
* In distance-based clustering algorithms we use a similarity function to measure the closeness between the text objects (copied, mining text data clustering)
* Cosine similarity function is the most commonly used for text purposes
* Two common distance-based approaches to clustering are agglomerative hierarchical clustering, and distance-based partitioning.
* K-means and K-medoid are the most commonly used algorithms for distance based partitioning.
K-medoid requires a larger number of iterations, and doesn't work as well for sparse data such as text (mining text data clustering chapter)

#### K-means clustering

* The k-means clustering algorithm also uses a set of k representatives around which the clusters are built.
* Simplest form -- Select k seeds from the original corpus. Assign documents to these seeds on the basis of closest similarity
* Before each new iteration, select a new centroid that is the best central point for each cluster is selected. Repeat until convergence.
* Include demonstrative images
* One advantage: K-means converges after a small number of iterations.
* Another lightweight clustering method might be used to select initial seeds
* K-means++ selecting initial seeds http://ilpubs.stanford.edu:8090/778/1/2006-13.pdf

#### Hierarchical clustering

#### Word embeddings: Word2Vec

### Text Classification

* Widely studied
* Set of training records (in this case, text documents).
    * They are labeled with one of k discrete classes
    * This is used to create a classification model
    * Then this model can be used to predict the labels of previously unseen labels
* Some models can also give you a probability of a document belonging to a certain class, while others are margin-based, and the distance from the margin can be used to indicate how certain the model are. -- refer to support vector machines for classification original paper
* Usages
    * News filtering
    * Document retrieval
    * Emails
* Models
    * Decision trees
    * Neural networks
    * SVM
* Here we mainly use SVM, since it has been studied extensively in the context of active learning -- cite a bunch of papers that have used it

#### SVM

#### Multi-Label Classification

### Active Learning

* Compared to random
* Initial sample selection to get a rough idea of the decision boundary.
    * Introduces sampling bias

#### Pool-based vs Stream based

#### The Version Space

* In machine learning hypothesis is a specific configuration of a model, the purpose of which is to predict outputs on new instances of data by generalizing the training data.
    * For example: An SVM with some defined values for the different parameters.
* Hypothesis space: All possible hypothesis that we are currently taking into account
    * Denote with H and the formula 
    * For example, the set of all possible values for the different parameters for SVM
* Version space: Subset of hypothesis space that is consistent with the data
    * Correct predictions for the labeled data. (L -- make sure to introduce in pool-based)
    * If we assume that one of these hypothesis can explain the data perfectly: Obtaining more labeled samples will shrink the version space.
* Knowing this, the task of the active learning algorithm then becomes to choose the data instances that will reduce the size of the version space as quickly as possible
* 

#### Binary Minimization

#### MMC