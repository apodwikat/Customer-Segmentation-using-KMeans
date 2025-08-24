# Customer Segmentation using K-Means (Implemented from Scratch)

### Author: Eng. Abdallah Dwikat
### Organization: Elevvopath Intern
### Date: 24th of August 2025

This project demonstrates how to build a K-Means clustering algorithm from scratch to segment mall customers into meaningful groups based on their Annual Income and Spending Score. Unlike using prebuilt libraries, this implementation manually handles centroid initialization, cluster assignment, and centroid updating, providing deeper insight into how K-Means works under the hood.

Project Overview
## Dataset
File: Mall_Customers.csv
Size: 200 rows × 5 columns
Columns: CustomerID, Gender, Age, Annual Income (k$), Spending Score (1-100)

## Workflow
Load and inspect dataset
Select features (Annual Income, Spending Score)
Visualize original data distribution
Implement K-Means clustering from scratch
Determine optimal clusters using Elbow Method
Fit K-Means with k=5 (optimal)
Visualize clusters and centroids
Analyze customer segments by average age, income, and spending behavior

## Implementation Details
### 1. Data Preprocessing

Selected features:
X = df[['Annual Income (k$)', 'Spending Score (1-100)']].values
Basic scatter plot to view the data distribution.

### 2. K-Means Algorithm (Custom Implementation)
class SimpleKMeans:
    def __init__(self, k=3, max_iters=100):
        self.k = k
        self.max_iters = max_iters
        ...
Centroids initialized randomly (reproducible with np.random.seed(42)).
Algorithm stops when centroids do not significantly move (convergence).

### 3. Optimal Number of Clusters

Elbow Method: Plotted cost (WCSS) vs. k (1–7).
Optimal k = 5 (clear elbow point).

### 4. Final Model

Fitted SimpleKMeans(k=5) on feature matrix X.
Converged after 11 iterations.

## Results
Cluster Visualization

Customers grouped into 5 clusters.

Distinct spending patterns observed:

Some clusters represent high income & high spending customers.

Others represent low income or low spending segments.

Cluster Analysis
Cluster 1 (80 customers):
  Average Age: 42.9
  Average Income: $55k
  Average Spending Score: 49.7

Cluster 2 (22 customers):
  Average Age: 25.3
  Average Income: $26k
  Average Spending Score: 79.4

Cluster 3 (23 customers):
  Average Age: 45.2
  Average Income: $26k
  Average Spending Score: 20.9

Cluster 4 (39 customers):
  Average Age: 32.7
  Average Income: $87k
  Average Spending Score: 82.1

Cluster 5 (36 customers):
  Average Age: 40.7
  Average Income: $88k
  Average Spending Score: 17.6


## Key Insight:

Segments reveal both income-based and behavior-based groupings, useful for targeted marketing.

High-income groups can have either very high or very low spending scores, suggesting different customer mindsets.

## Requirements

Install dependencies:

pip install pandas numpy matplotlib

## How to Run

Download the dataset Mall_Customers.csv.

Update the dataset path in the script:

df = pd.read_csv(r"C:\Users\hp\Elevvopath\2) Customer_Segmentation_KMeans\Mall_Customers.csv")

Run the Python script.

View generated plots and printed cluster analysis.

## Future Enhancements

Compare results with scikit-learn KMeans to validate accuracy.

Extend to 3D clustering using Age + Income + Spending Score.

Add automatic k selection using Silhouette Score.

We successfully segmented mall customers into 5 meaningful groups! 🎉

## Author: Eng. Abdallah Dwikat
## Date: 24th of August 2025
