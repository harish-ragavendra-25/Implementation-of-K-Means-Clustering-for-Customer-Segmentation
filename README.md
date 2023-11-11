# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas and matplot libraries.
2. import Kmeans algorithm to solve customer segmentation.
3. Using the for loop cluster the given data
4. Predict the output and plot data graphs. 5.Display the outputs 
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: HARISH RAGAVENDRA S
RegisterNumber:  212222230045
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers.csv")
print('data.head():')
data.head()
print('data.info():')
data.info()
print('isnull() and sum():')
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
print('Elbow method diagram:')
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
print('KMeans():')
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
print('array():')
y_pred=km.predict(data.iloc[:,3:])
y_pred
print('Customer segments diagram:')
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer segments")
```

## Output:
![Screenshot 2023-11-11 170701](https://github.com/harish-ragavendra-25/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/114852180/5b42b82e-bf03-4dbe-b83b-34a4158e548a)
![Screenshot 2023-11-11 170706](https://github.com/harish-ragavendra-25/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/114852180/03863b5b-5592-411f-a91f-0c4a589b8a08)
![Screenshot 2023-11-11 170711](https://github.com/harish-ragavendra-25/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/114852180/15e1ecfb-7633-495a-b4e1-66898dbd4dcb)
![Screenshot 2023-11-11 170717](https://github.com/harish-ragavendra-25/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/114852180/8820f2cf-e24f-442d-bc91-489f12f55fce)
![Screenshot 2023-11-11 170735](https://github.com/harish-ragavendra-25/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/114852180/5c5ed508-7c6b-428d-a956-5093ef6c4f45)
![Screenshot 2023-11-11 170741](https://github.com/harish-ragavendra-25/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/114852180/387d538f-12d3-47da-8b52-2aa0961fef3c)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
