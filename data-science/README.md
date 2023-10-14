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
