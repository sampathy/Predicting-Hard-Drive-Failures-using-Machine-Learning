# Predicting Hard-Drive Failures using Machine Learning 

## Team: Group-02

* Asanga Ramanayaka
* Gamage Upeksha Maduwanthi Perera
* Shadi Moradi
* Venkata SaiRam Sampath Yelchuri


## Summary:

### About this project:

* The goal of this project is to analyze given data and find out meaningful information that can help determine drives failure trends and different factors that may indicate if a drive would fail, and attempt to propose a more data driven answer to future failures based on SMART metrics.

### Selected Dataset:

* For this study, we have selected the Backblaze hard drive dataset for first quarter of 2017 (1st of January to 31st of March). Backblaze dataset contains millions of records of hard drive data from 2013 to 2019. There are many columns (85 + columns) available in each file containing SMART variable. SMART attribute (Self-Monitoring, Analysis and Reporting Technology) is a software monitoring system for hard drives. SMART generates a collection different metrics related to help evaluate the overall health of a Hard Drive.

* The selected dataset, 2017 Q1 dataset, has 6.5 million hard drive data in total and 385 failed hard drive containing information about Seagate, Hitachi, Western Digital, Toshiba models. In this project we splited 2017 first quarter dataset into four based on manufacturer and ran predictive analysis on each dataset separately using machine learning techniques.

### Techniques and Results:

* As mentioned earlier, there are only 385 failed hard drives out of 6.4 million sampled hard drive; this means that the data is highly imbalanced and sparse. To tackle this problem we have applied three oversampling techniques, namely SMOTE, SVMSMOTE, and ADASYN. These oversampling techniques, generate synthetic data similar to the minority class in order to balance the dataset. Additionally, we have applied Recursive Feature Elimination to select the best features for prediction, in addition to reducing the dataset size since we are dealing with a huge dataset. Finally, the following machine leaning approaches, namely Decision Tree Classifier, Random Forest, Support Vector Machine, Ada Boost, and Logistic Regression are applied on the data to detect the failures. 

* In a nutshell, inside a 5-fold cross-validation we first divided the data into training and testing sets. Then applied the aforementioned oversampling techniques on just the training dataset. Then, using recursive feature selection (RFE) we have selected top five features based on their ranking number and Finally after selecting the classifier model and fitting the oversampled training dataset we predicted the failure.

* By trying the aforementioned machine learning classifiers, oversampling techniques, and RFE, each group members obtained different sets of features. However, the literature identifies nine raw SMART parameters, which are number 5, 12, 187, 188, 189, 190, 198, 199 and 200, as important predictor parameters. We compared the results that we obtained using RFE to the literature, in some models RFE works better and in some models like Seagate RFE performed the same as the literature.

* Based on the results for all four models, Random Forest Classifier with SMOTE oversampling technique worked the best in detecting the hard drive failures in testing data and having the least false alarm considering the confusion matrix. 

