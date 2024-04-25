# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas and matplotlib.pyplot
2. Read the dataset and transform it
3. Import KMeans and fit the data in the model
4. Plot the cluster graph
 

## Program:
```

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Padmashree R
RegisterNumber:  212222040110

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[] # With-Cluster Sum of square
# It is the of squared distance between each point & the centroid in a cluster.

for i in range (1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="yellow",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:

![image](https://github.com/Bosevennila/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870486/2794075c-6fa7-4657-9a0a-4801cd8b5c91)

![image](https://github.com/Bosevennila/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870486/3194673b-293f-4271-bd1a-4e1b08382fc8)

![image](https://github.com/Bosevennila/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870486/44e24cfd-ed23-44d4-8b55-b6f46b843193)

![image](https://github.com/Bosevennila/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870486/a2880423-2119-44d0-bbea-dab3e0a826bb)

![image](https://github.com/Bosevennila/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870486/b4a8a12d-d4d3-4aaf-99e7-9c8191d8e507)

![image](https://github.com/Bosevennila/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870486/c1c5d599-44ad-4018-8426-d3d3aeb9d534)

![image](https://github.com/Bosevennila/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870486/3994f0a6-4ef0-4739-b8b8-bb76a58ebe69)

![image](https://github.com/Bosevennila/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870486/98623a1d-0ddf-4b04-b24c-04829be7b0cf)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
