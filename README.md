## Cryptocurrency Clustering Analysis
Overview
This analysis involves clustering cryptocurrencies using both the original scaled data and PCA-transformed data. The goal is to find the optimal number of clusters (k) for K-Means clustering and compare the results between the original and PCA-reduced data.

### Note: As the code uses hvplot, the graphs will not appear in Github. Please download and run to view the plots.

### Steps and Results
1. Finding the Best Value for 𝑘 using the Original Scaled DataFrame
The optimal k value was determined using the elbow method with the following steps:

List Creation: 
A list of 𝑘: k values ranging from 1 to 11 was created.
Inertia Calculation: An empty list was initialized to store the inertia values. A for loop computed the inertia for each value of 𝑘
Data Preparation: A dictionary was created with the computed inertia values for plotting the elbow curve.
Plotting: A line chart was plotted to visualize the inertia values and identify the optimal 𝑘


2. Clustering Cryptocurrencies with K-Means Using the Original Scaled Data
Clustering was performed using the original scaled data with the best k value:

Model Initialization: The K-means model was initialized with the best value for k.
Model Fitting: The model was fitted using the original scaled DataFrame.
Cluster Prediction: Clusters were predicted to group the cryptocurrencies.
Data Augmentation: A copy of the original data was made, and a new column with the predicted clusters was added.
Scatter Plot: A scatter plot was created using hvPlot with the following settings:
X-axis: "price_change_percentage_24h"
Y-axis: "price_change_percentage_7d"
Coloring: Points were colored by K-means labels.
Hover Information: The "coin_id" column was added to identify each cryptocurrency.

3. Optimizing Clusters with Principal Component Analysis (PCA)
PCA was used to reduce the features to three principal components:

Explained Variance: The explained variance was retrieved to assess how much information each principal component captured.
Total Explained Variance: The total explained variance of the three principal components was found to be 𝑌
A new DataFrame with the PCA data was created, setting the "coin_id" index from the original DataFrame.

4. Finding the Best Value for k Using the PCA Data
The elbow method was used to find the optimal k value for the PCA-transformed data:

List Creation: 
A list of k values from 1 to 11 was created.
Inertia Calculation: An empty list was used to store inertia values. A for loop computed the inertia for each k.
Data Preparation: A dictionary was created with the computed inertia values for plotting the elbow curve.
Plotting: A line chart was plotted to visualize the inertia values and determine the optimal k.

Comparison: This value was compared with the best k found using the original data.

5. Clustering Cryptocurrencies with K-Means Using the PCA Data Clustering was performed using the PCA data with the best k value:

Model Initialization: The K-means model was initialized with the best value for k.
Model Fitting: The model was fitted using the PCA data.
Cluster Prediction: Clusters were predicted for the PCA data.
Data Augmentation: A copy of the PCA data DataFrame was made, and a new column was added to store the predicted clusters.
Scatter Plot: A scatter plot was created using hvPlot with the following settings:
X-axis: "PC1"
Y-axis: "PC2"
Coloring: Points were colored by K-means labels.
Hover Information: The "coin_id" column was included to identify each cryptocurrency.
Questions
Best Value for k: What is the best value for k using the original scaled data and PCA data?
Impact of Feature Reduction: What is the impact of using fewer features to cluster the data using K-Means?
