# Credit-Card-Fraud-Detection
<div align="justify">
This repository contains the methodology that is used for the identification of the credit card fraud detection through Machine Learning.

The dataset used is Credit Card Fraud Detection Dataset 2023 from Kaggle. It consists of about 550,000 transactions records made by the European card holders in 2023 and to protect the cardholders identities the data has been anonymized. The primary objective of this dataset is to facilitate the development of fraud detection algorithms and models to identify potentially fraudulent transactions.

**Overview of the Framework:**
1) Load the dataset: &emsp;[![Kaggle Dataset](https://img.shields.io/badge/Kaggle-Dataset-blue)](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud/data)
2) Data pre-processing : Resampling Technique - SMOTE, RUS
3) Feature Selection Techniques : <br>
   (i) SelectKBest (Filter-Based Technique),   <br>
   (ii) Recursive Feature Elimination (Wrapper Technique)   <br>
   (iii) Embedded Method   <br>
4) Hyperparameter Optimization : PSLPSO (gives optimal solution for C and Sigma)
5) Splitting the data
6) Classification : SVDD, ADABoost, XGBoost, LR, DT, SVM, KNN, RF
7) Evaluation Metrics : Accuracy, Precision, Recall, F1 Score, ROC Curve
8) Results :   <br>
   (I)  Model Performance without FST   <br>
   (II) Model Performance with FST   <br>
   &emsp;(i)   Performance measures using Filter FST   <br>
   &emsp;(ii)  Performance measures using Wrapper FST   <br>
   &emsp;(iii) Performance measures using Embedded FST   <br>
<br>

***Resampling Technique:*** *SMOTE* - Synthetic Minority Oversampling Technique   <br><br>
(1) SMOTE is a Oversampling Technique that is applied on the Minority Class to upsample the datapoints that belongs to the minority class inorder to create a balanced dataset.   <br>
(2) Since duplication leads to overfitting conditions in ROS (RandomOverSampler), SMOTE on the otherhand generates a new datapoints due to which -    <br>
&emsp;(i)  Balance is achieved   <br>
&emsp;(ii) Overfitting problem is also solved   <br>
(3) How to generate new datapoints?   <br>
&emsp;&emsp;SMOTE uses *"Interpolation Technique"* which creates a new datapoint in between the already existing two minority datapoints.   <br>
(4) Train a KNN on minority class observations - find each observation's 5 closest neighbours (generally k=5 is considered).   <br>
(5) To create a new synthetic data :   <br>
&emsp;(i)   Select the samples from the minority class at random   <br>
&emsp;(ii)  Select a neighbour of each sample at random (for the interpolation)   <br>
&emsp;(iii) Extract a random number between 0 and 1   <br>
&emsp;(iv)  Calculate the new synthetic samples/datapoints as -
<div align="center">original sample - factor * (original sample - neighbour)</div>
(6) The final dataset consists of the original dataset + the newly created synthetic samples.
</div>
