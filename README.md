# Personalized-Cancer-Redefining-Cancer-Treatment-

Problem statement : 
Classify the given genetic variations/mutations based on evidence from text-based clinical literature.

DATA: 
Source: https://www.kaggle.com/c/msk-redefining-cancer-treatment/data <br>
We have two data files: one conatins the information about the genetic mutations and the other contains the clinical evidence (text) that human experts/pathologists use to classify the genetic mutations.<br>
Both these data files are have a common column called ID<br>


Data file's information:<br>
training_variants (ID , Gene, Variations, Class)<br>
training_text (ID, Text)<br>

<h3> UNIVARIATE ANALYSIS </h3>

![Screenshot (76)](https://user-images.githubusercontent.com/48092244/64754092-578e9d00-d543-11e9-96e7-3c2e4a1450d4.png)

#### OBSERVATIONS: 
1] The text feature gives most of the information and has less cv and train loss.<br>
2] We have added new feature "gene+variation" which is the combination of gene and variation feature.<br> 
3] By applying TFIDF on top of this feature we get 1.112 test loss which is better than the individual loss of Gene and Variation feature.

<h3> STACKING </h3>

![Screenshot (77)](https://user-images.githubusercontent.com/48092244/64754177-d7b50280-d543-11e9-8775-9f6d60274b9f.png)

#### OBSERVATIONS: 
1] Here we stack different features together and applied logistic regression on top of it.<br>
2] When we stack "Gene", "gene+variation","text" we get less cv and test loss. Also the missclassification is less. So we select this stack for implementing different models.

<h3>Training Different Models</h3>

![Screenshot (78)](https://user-images.githubusercontent.com/48092244/64754234-1ba80780-d544-11e9-95a9-30b7bf40e0b5.png)

#### OBSERVATIONS:
1] Logistic Regression, SVM, RandomForest - Response coding and voting classifier performed well.<br>
2] The misclassification is less for Logistic Regression.
