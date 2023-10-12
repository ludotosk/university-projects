# Ludovico Toscano university projects repository
Welcome to the repository with some of mine university projects. 👋

## Machine learning
### Clustering - [jupiter notebook here](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project3/Project%203%20.ipynb)

This project was about a dataset created by my professor for a paper he wrote, with customer data given by an Hotel in Lisbon. The objective was to cluster the customers in order to find the best way to target them with marketing campaigns.

To create the clusters we used **Principal Component Analysis** and **K-means** algorithm. Then we used the **Elbow** and **Silhouette** method to try to define the best number of clusters, and in order to make the final decision we looked to the values of the **Centroids**, **Cardinality**, **Magnitude** and **Intercluster Distance**.

### Classification - [EDA notebook](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project2/Project2-README.ipynb)

This project was about predicting if a supermarket customer will accept a marketing campaign or not, the data of this project are provided by ifood but the dataset has some changes made by the professor. The objective was to test different classification algorithms and compare them. 

We tried different ways to deal with **imbalanced learning**, such as **undersampling** and **oversampling** using **SMOTE**. For the fine tuning process we used **Grid Search** and for the logistic regression we also used **recursive feature elimination** in order to help us to choose wich feature to keep.

| Algorithm used         | Notebook                                                                                                                                 |
|------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| Decision Tree          | [link](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project2/Project2-%20DT.ipynb)                              |
| Logistic Regression    | [link](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project2/Project2-%20Logistic%20Regression.ipynb)           |
| Naive Bayes            | [link](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project2/Project2-%20Na%C3%AFve%20Bayes%20Classifier.ipynb) |
| Neural Network         | [link](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project2/Project2-%20Neural%20Network.ipynb)                |
| Support Vector Machine | [link](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project2/Project2-%20SVM.ipynb)                             |
| K-Nearest Neighbors    | [link](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project2/Project2-%20KNN.ipynb)                             |

### Regression - [EDA notebook](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project1/Data_preparation_and_exploration_group_E.ipynb)

In this project we tried to use different regression algorithms to predict the popularity of a song based on some meta data provided by Spotify. As you can see on the exploratory data analysis we found other work based on similar data set but with some extra features and 10 times more data. Even in that case is hard to have a good prediction because this meta data aren't the right one to look at for this task, that was said also by the professor.

We used **Linear Regression** and **Decision Tree** to complete the task, we also tried with a **Neural Network** but it wasn't performed well so we didn't went further with it. That was our first project after the beginning of the class of Machine Learning so it's the less complete of the three.

| Algorithm used    | Notebook                                                                                                |
|-------------------|--------------------------------------------------------------------------------------------------------------|
| Decision Tree     | [link](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project1/DT_Group_E.ipynb) |
| Linear Regression | [link](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project1/LR_Group_E.ipynb) |

## Big data
### PySpark - [data bricks notebook here](https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/8951170136253674/4022108160822800/7461935275397430/latest.html)

For this project it was asked to find a dataset and then using PySpark do something, like a Machine Learning model for example. The ML model wasn't evaluated, we only need to use in the right way the PySpark functions.

So we did an Exploratory Data Analysis of a dataset of a Brasilian e-commerce in order to predict the score for each order. Then we used a multinomial linear regression to predict the score.

## Social media analytics

All this sections are part of the same of the same project, the objective was to scrape some data from the web and then apply some of the **Text mining** tecniques that we have learn on class.

### Scraping

For doing the **Text mining** analysis we had to scrape some data from the web, so we have chose to scrape some articles and comments from three different news papers in order to see if we are able to find any difference in the way they treat the argument of the war in Ukraine.

| News Paper       | Data                | Notebook                                                                                                                       |
|------------------|---------------------|--------------------------------------------------------------------------------------------------------------------------------|
| Daily Mail       | Articles + Comments | [link](https://github.com/ludotosk/university-projects/blob/main/social-media-analytics/dailymail/daily_mail.ipynb)            |
| Fatto Quotidiano | Articles            | [link](https://github.com/ludotosk/university-projects/blob/main/social-media-analytics/fatto-quotidiano/scraper_falso.ipynb)  |
| Fatto Quotidiano | Comments            | [link](https://github.com/ludotosk/university-projects/blob/main/social-media-analytics/fatto-quotidiano/comments_falso.ipynb) |
| Sputnik          | Articles            | [link](https://github.com/ludotosk/university-projects/blob/main/social-media-analytics/sputnik/sputnik.ipynb)                 |
| Sputnik          | Comments            | [link](https://github.com/ludotosk/university-projects/blob/main/social-media-analytics/sputnik/CreateCommentDSsputnik.ipynb)  |

### Text mining

We decide to perform **Topic Modeling**, **Frequency Analysis**, **Keyword Extraction** and **Sentiment Anlysis**.

Notebooks are coming, I need to clean the cells output and add explanations. In the meantime you can take a look on the [report](https://github.com/ludotosk/university-projects/blob/main/social-media-analytics/SMA%20Report.docx.pdf) that we have made.