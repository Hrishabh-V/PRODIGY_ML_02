# Mall Customer Clustering Project

## Overview

This project implements a clustering pipeline for customer segmentation in a retail environment using the Mall Customers dataset. By employing unsupervised learning techniques, we aim to identify distinct customer groups based on their purchasing behavior and demographics, enabling targeted marketing strategies and enhanced customer satisfaction.

## Dataset

The dataset used for this analysis is the **Mall_Customers.csv**, which contains the following features:

- **CustomerID**: Unique identifier for each customer
- **Gender**: Gender of the customer (Male/Female)
- **Age**: Age of the customer
- **Annual Income (k$)**: Annual income of the customer in thousands
- **Spending Score (1-100)**: Score assigned by the mall based on customer spending behavior

## Clustering Pipeline

The main components of the clustering pipeline are as follows:

1. **Data Preprocessing**: 
   - Handling missing values and encoding categorical features (e.g., Gender).
   - Scaling numerical features to ensure uniformity in distances.

2. **K-Means Clustering**:
   - Utilizing the K-Means algorithm to segment customers into distinct clusters.
   - The optimal number of clusters is determined using the **Elbow Method**.

3. **Visualization**:
   - Visualizing the clusters using scatter plots to assess the distribution and characteristics of each group.

4. **Prediction for New Customers**:
   - A function to predict the cluster for a new customer based on their demographic data.

## The Elbow Method

The **Elbow Method** is a heuristic used to determine the optimal number of clusters (K) for K-Means clustering. The method involves the following steps:

1. **Calculate the Within-Cluster Sum of Squares (WCSS)** for different values of K. WCSS measures the total distance between data points and their respective cluster centroids, with lower values indicating better clustering.

2. **Plot WCSS against the number of clusters (K)**. 

3. **Identify the "elbow" point** on the plot, where the rate of decrease in WCSS sharply changes. This point suggests a good trade-off between the number of clusters and the compactness of the clusters.

### Why Use the Elbow Method?

The Elbow Method helps prevent overfitting by ensuring that we do not choose too many clusters, which can lead to unnecessarily complex models. It balances simplicity and accuracy, aiding in the selection of the most effective K for the clustering task.

## K-Nearest Neighbors (KNN)

**K-Nearest Neighbors (KNN)** is a supervised learning algorithm used for classification and regression. In this project, KNN is implemented for predicting the cluster of new customers based on their features. Here's how KNN works:

1. **Select the number of neighbors (K)**: This determines how many nearby data points will influence the prediction.

2. **Calculate the distance** from the new customer to all existing customers in the feature space. Common distance metrics include Euclidean distance and Manhattan distance.

3. **Identify the K nearest customers** based on the calculated distances.

4. **Assign the cluster label**: The new customer is classified into the cluster most common among its K nearest neighbors, using majority voting.

### Uses of KNN

- **Classification**: Predicting the category or cluster of new data points based on their similarity to existing points.
- **Recommendation Systems**: Finding similar items or users based on features and preferences.
- **Anomaly Detection**: Identifying outliers by measuring the distance of data points from their neighbors.

## Implementation of the Project

### Key Steps in Implementation

1. **Data Loading**: Load the dataset and examine its structure.

2. **Data Preprocessing**: 
   - Encode categorical variables (e.g., Gender) using label encoding.
   - Scale numerical features (Age, Income, Spending Score) using StandardScaler to standardize their ranges.

3. **Elbow Method**: 
   - Compute WCSS for a range of K values and plot the results.
   - Identify the optimal K from the elbow point.

4. **K-Means Clustering**:
   - Fit the K-Means model using the optimal K and obtain the cluster assignments for each customer.

5. **Visualization**: 
   - Use scatter plots to visualize the clusters and their characteristics.

6. **New Customer Prediction**:
   - Implement a function to predict the cluster for a new customer using KNN, allowing users to categorize new entries based on existing clusters.

7. **Output**: 
   - Display the clustered data and the prediction results.

## Conclusion

This project demonstrates the effectiveness of K-Means clustering for customer segmentation and the utility of KNN for predicting customer behavior. The insights gained from this analysis can be leveraged for targeted marketing strategies, improving customer engagement, and driving sales growth.
