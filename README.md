# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
 Step 1: Start

 Step 2: Data Preparation: Load and explore customer data.
 
 Step 3: Determine Optimal Clusters: Use the Elbow Method to find the best number of clusters.
 
 Step 4: Apply K Means Clustering: Perform clustering on customer data.
 
 Step 5: Visualize Segmented Customers: Plot clustered data to visualize customer segments.
 
 Step 6: End

## Program:
### Program to implement the K Means Clustering for Customer Segmentation.
#### Developed by: VESLIN ANISH A
#### RegisterNumber:  212223240175
```python
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No of Cluster")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

KMeans(n_clusters=5)

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"]=y_pred
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
plt.title("Customer Segments")
```
## Output:

![image](https://github.com/user-attachments/assets/de3a9a42-3a88-4861-9b0c-06836154668a)

#### y_pred
![image](https://github.com/user-attachments/assets/a21b62fe-f81d-433c-9e7e-96bf2e06040c)

#### Cluster
![image](https://github.com/user-attachments/assets/5b0765e9-57f1-4cd4-978d-d34d4d963505)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
