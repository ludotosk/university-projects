# Ludovico Toscano portfolio
Welcome to the repository with some of my university projects. 👋

- **Subjects**:
    - [Machine learning](#machine-learning)
    - [Data Mining](#data-mining)
    - [Big data](#big-data)
    - [Social media analytics](#social-media-analytics)

## Machine learning
### Clustering - [jupiter notebook here](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project3/Project%203%20.ipynb)

This project was about a dataset created by my professor for a paper he wrote, with customer data given by a Hotel in Lisbon. The objective was to cluster the customers in order to find the best way to target them with marketing campaigns.

To create the clusters we used **Principal Component Analysis** and **K-means** algorithm. Then we used the **Elbow** and **Silhouette** methods to try to define the best number of clusters, and in order to make the final decision we looked at the values of the **Centroids**, **Cardinality**, **Magnitude**, and **Intercluster Distance**.

### Classification - [EDA notebook](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project2/Project2-README.ipynb)

This project was about predicting if a supermarket customer will accept a marketing campaign or not, the data of this project are provided by Ifood but the dataset has some changes made by the professor. The objective was to test different classification algorithms and compare them. 

We tried different ways to deal with **imbalanced learning**, such as **undersampling** and **oversampling** using **SMOTE**. For the fine-tuning process, we used **Grid Search** and for the logistic regression, we also used **recursive feature elimination** in order to help us to choose which feature to keep.

| Algorithm used         | Notebook                                                                                                                                 |
|------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| Decision Tree          | [link](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project2/Project2-%20DT.ipynb)                              |
| Logistic Regression    | [link](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project2/Project2-%20Logistic%20Regression.ipynb)           |
| Naive Bayes            | [link](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project2/Project2-%20Na%C3%AFve%20Bayes%20Classifier.ipynb) |
| Neural Network         | [link](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project2/Project2-%20Neural%20Network.ipynb)                |
| Support Vector Machine | [link](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project2/Project2-%20SVM.ipynb)                             |
| K-Nearest Neighbors    | [link](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project2/Project2-%20KNN.ipynb)                             |

### Regression - [EDA notebook](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project1/Data_preparation_and_exploration_group_E.ipynb)

In this project, we tried to use different regression algorithms to predict the popularity of a song based on some metadata provided by Spotify. As you can see on the exploratory data analysis we found other work based on similar data sets but with some extra features and 10 times more data. Even in that case is hard to make a good prediction because this meta data aren't the right ones to look at for this task, which was said also by the professor.

We used **Linear Regression** and **Decision Tree** to complete the task, we also tried with a **Neural Network** but it didn't perform well so we didn't go further with it. That was our first project after the beginning of the class of Machine Learning so it's the less complete of the three.

| Algorithm used    | Notebook                                                                                                |
|-------------------|--------------------------------------------------------------------------------------------------------------|
| Decision Tree     | [link](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project1/DT_Group_E.ipynb) |
| Linear Regression | [link](https://github.com/ludotosk/university-projects/blob/main/machine-learning/project1/LR_Group_E.ipynb) |

## Data mining
### National Tourism Promotion - [EDA](https://github.com/ludotosk/university-projects/blob/main/data%20science/Group_40.ipynb) - [Report](https://github.com/ludotosk/university-projects/blob/main/data%20science/Report_Group40.pdf)
#### Project description

Goal: Provide business recommendations to the National Tourism Board Organizations (NTBO) of Portugal in order to increase 
tourism activity in Portugal.

Our professor gave us three different datasets, one contained some reviews scraped by trip advisor, the second one contained data about the attractions about the scraped comments and the last one was about holiday dates in the world.

We had to perform **data mining** techniques in order to make a report with all the findings and the business recommendations. We also had to find a way to perform **RFM**, **Apriori**, and the **Cosine similarity** in a way that can fit our needs.

Using the **Apriori** we were able to discover the combinations of attractions that are more likely to be visited together, and using the **Cosine similarity** we were able to find the attractions that are more similar to each other.

Then we performed the **RFM** in order to find influencers on our dataset, based on the number of contributions, the number of reviews, and the rating given. The rating for us was important since those who give a higher rating are more likely to give good reviews if we invite them to visit Portugal.

#### Data Preparation

As said before we had one dataset with the reviews, that was containing also the location of the user but it wasn't registered in a consistent way. Something was given the name of the nation, and other times the name of the city so in order to perform some clustering we had to find the ISO code of the nation of each user. To do that we leveraged two libraries **Geopy** and **Pycountry**, the first one is able to search the location on the **OpenStreetMap** dataset and the second one is able to give us the ISO code of the nation given the name.

##### Finding users ISO code - [First Pycountry notebook](https://github.com/ludotosk/university-projects/blob/main/data%20science/userLocationPycountryFirst_group40.ipynb) - [Geopy notebook](https://github.com/ludotosk/university-projects/blob/main/data%20science/userLocationGeopy_group40.ipynb) - [Second Pycountry notebook](https://github.com/ludotosk/university-projects/blob/main/data%20science/userLocationPycountrySecond_group40.ipynb)

The first problem to solve was that the Geopy APIs have some constraints on the number of requests that you can do, so in order to not spend the 12 hours needed to obtain the data we had to reduce the number of queries needed.

So we first included the observations that already have the ISO code, and for those with the name of the country we used Pycountry to find the ISO code. We then noticed that for the USA states a code similar to the ISO one was given, so we changed all this code to USA. We also noticed some UK code from the scraped data that we changed with GBR.

Then we performed the Geopy query only for the ones that were missing the ISO code, reducing the search time to half an hour. That was important since we had found some problems with the data so we performed this process many times. Then we used the new data to perform another time the Pycountry search in order to transform the name of the nation in the ISO code.

##### Finding attractions coordinates - [Notebook](https://github.com/ludotosk/university-projects/blob/main/data%20science/geopyAttraction_group40.ipynb)

For the attractions we used the Geopy APIs to find the coordinates of the attractions, we had to do this because the dataset contained the name of the attraction and the country but not the coordinates. The coordinates were important because we found out that within big countries there are different clusters of attractions, and if an attraction is on the border between two countries it needs to fall in the same cluster.

So we first used Geopy to have the coordinates, then since we had only 100 attractions we were able to inspect the results and correct some of the wrong findings. So we performed **K-means** with different numbers of k with a range that was bigger than the number of the analyzed nations, so we already know that isn't enough. Then we took a look into the results until the clusters started to make sense with what we studied in the business understanding part.

## Big data
### PySpark - [data bricks notebook here](https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/8951170136253674/4022108160822800/7461935275397430/latest.html)

For this project, it was asked to find a dataset and then using PySpark do something, like a Machine Learning model for example. The ML model wasn't evaluated, we only need to use it in the right way the PySpark functions.

So we did an Exploratory Data Analysis of a dataset of a Brazilian e-commerce in order to predict the score for each order. Then we used a multinomial linear regression to predict the score.

## Social media analytics

All these sections are part of the same project, the objective was to scrape some data from the web and then apply some of the **Text mining** techniques that we have learned in class.

### Scraping

For doing the **Text mining** analysis we had to scrape some data from the web, so we chose to scrape some articles and comments from three different newspapers in order to see if we are able to find any difference in the way they treat the argument of the war in Ukraine.

| News Paper       | Data                | Notebook                                                                                                                       |
|------------------|---------------------|--------------------------------------------------------------------------------------------------------------------------------|
| Daily Mail       | Articles + Comments | [link](https://github.com/ludotosk/university-projects/blob/main/social-media-analytics/dailymail/daily_mail.ipynb)            |
| Fatto Quotidiano | Articles            | [link](https://github.com/ludotosk/university-projects/blob/main/social-media-analytics/fatto-quotidiano/scraper_falso.ipynb)  |
| Fatto Quotidiano | Comments            | [link](https://github.com/ludotosk/university-projects/blob/main/social-media-analytics/fatto-quotidiano/comments_falso.ipynb) |
| Sputnik          | Articles            | [link](https://github.com/ludotosk/university-projects/blob/main/social-media-analytics/sputnik/sputnik.ipynb)                 |
| Sputnik          | Comments            | [link](https://github.com/ludotosk/university-projects/blob/main/social-media-analytics/sputnik/CreateCommentDSsputnik.ipynb)  |

### Text mining

We decided to perform **Topic Modeling**, **Frequency Analysis**, **Keyword Extraction**, and **Sentiment Analysis**.

Notebooks are coming, I need to clean the cell's output and add explanations. In the meantime, you can take a look at the [report](https://github.com/ludotosk/university-projects/blob/main/social-media-analytics/SMA%20Report.docx.pdf) that we have made.
