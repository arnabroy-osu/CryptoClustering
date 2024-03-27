## Title
Module 11 Challenge - Crypto Clustering

## Source Data
Crypto market Source data is pulled from a CSV file file `crypto_market_data.csv` located in the Resources folder. The file has the coin_id which is the unique identifier for the coin, and the following columns for price change percentage over different time periods: 24 hours, 7 days, 14 days, 30 days, 60 days, 200 days and 1 year.
- coin_id
- price_change_percentage_24h
- price_change_percentage_7d
- price_change_percentage_14d
- price_change_percentage_30d
- price_change_percentage_60d
- price_change_percentage_200d
- price_change_percentage_1y

## Desired Outcome of the exercise
The desired outcome of the exercise is to cluster the crypto currencies based on the price change percentage over different time periods. The clustering will be done using K-means algorithm. The number of clusters will be determined using the elbow curve method. The clustering will be done on the 24 hours, 7 days, 14 days, 30 days, 60 days, 200 days and 1 year price change percentage columns. Next we try to optimize Clusters with Principal Component Analysis (PCA) and compare the results with the original clusters without PCA data. Finally we will try to find which feature has the strongest +ve and -ve influence on each Principal Component.

## Data Preparation
Data preparation is pretty straight forward. We will load the data from the CSV file into a Pandas DataFrame and Index the DataFrame on the coin_id column. We check for any missing values (and drop them if any) and then scale the data using the StandardScaler. The scaled data is then used to cluster the data using K-means algorithm. We will use the elbow curve method to determine the number of clusters to use for the K-means algorithm & plot the clusters for the optimal number of clusters. We then repeat the same setps using PCA to see if the clusters can be optimized.

## Data Analysis & Conclusion
The data is analyzed using K-means algorithm and PCA. The optimal number of clusters is determined using the elbow curve method. The most ooptimal value of K is found to be 4 both without PCA and with PCA. We found features having the strongest +ve and -ve influence on each Principal Component are listed below:
- First principal component (PCA1): price_change_percentage_24h has the strongest -ive influence AND price_change_percentage_200d has the strongest +ive influence
- Second principal component (PCA2): price_change_percentage_1y has the strongest -ive influence AND price_change_percentage_30d has the strongest +ive influence
- Third principal component (PCA3): price_change_percentage_60d has the strongest -ive influence AND price_change_percentage_7d has the strongest +ive influence