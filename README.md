# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import Necesary Libraries.
2. Perform Basic operations.
3. Implement Kmeans Clustering fro the Model.
4. Plot the graph of cluster
   
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: B VIJAY KUMAR
RegisterNumber:  212222230173
*/
```
##### Read the file using Pandas
```
import pandas as pd
df=pd.read_csv("Mall_Customers (2).csv")
df
```
##### Basic Operations
```
df.head()
df.info()
df.describe()
df.shape
```
##### NULL COUNTS ON RESPECTIVE FEATURES
```
df.isnull().sum()
```
##### Elbow method graph
```
from sklearn.cluster import KMeans
wc = []

for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(df.iloc[:,3:])
    wc.append(kmeans.inertia_)

import matplotlib.pyplot as plt
plt.plot(range(1,11), wc)
plt.xlabel("No of CLusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
```
##### KMeans clusters
```
km = KMeans(n_clusters = 5)
km.fit(df.iloc[:,3:])
```
##### y_pred
```
y_pred = km.predict(df.iloc[:,3:])
y_pred
```
##### Customers Segments Graph
```
df['cluster'] = y_pred
df0 = df[df['cluster'] == 0]
df1 = df[df['cluster'] == 1]
df2 = df[df['cluster'] == 2]
df3 = df[df['cluster'] == 3]
df4 = df[df['cluster'] == 4]

plt.scatter(df0["Annual Income (k$)"], df0['Spending Score (1-100)'], c = 'red', label = 'cluster0')
plt.scatter(df1["Annual Income (k$)"], df1['Spending Score (1-100)'], c = 'black', label = 'cluster1')
plt.scatter(df2["Annual Income (k$)"], df2['Spending Score (1-100)'], c = 'blue', label = 'cluster2')
plt.scatter(df3["Annual Income (k$)"], df3['Spending Score (1-100)'], c = 'green', label = 'cluster3')
plt.scatter(df4["Annual Income (k$)"], df4['Spending Score (1-100)'], c = 'magenta', label = 'cluster4')

plt.legend()
plt.title('Customer segments')
```
## Output:

##### data.head()

![image](https://github.com/VIJAYKUMAR22007124/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119657657/179281d3-624c-4f89-a99b-36ead88a45c6)


##### data.info()

![image](https://github.com/VIJAYKUMAR22007124/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119657657/504f1875-9739-424e-924d-673c04c2244d)


##### data.isnull().sum()

![image](https://github.com/VIJAYKUMAR22007124/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119657657/eb7d5419-70e5-426d-b67a-8468b1592419)


##### Elbow method graph

![image](https://github.com/VIJAYKUMAR22007124/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119657657/e1392916-3736-4949-826d-46d74cf06b3c)


##### KMeans clusters

![image](https://github.com/VIJAYKUMAR22007124/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119657657/fea45637-11ee-40a8-96b0-c3c9e7267064)


##### y_pred

![image](https://github.com/VIJAYKUMAR22007124/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119657657/c1222791-8a61-4bb2-9d3d-bcb41b50939d)


##### Customers Segments Graph

![image](https://github.com/VIJAYKUMAR22007124/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119657657/4f27a062-35ba-4e4a-a27c-aa13cf0a0cfe)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
