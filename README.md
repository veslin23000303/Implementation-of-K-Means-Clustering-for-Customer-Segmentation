# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
Step 1. Start the program.

Step 2. Import the necessary python libraries.

Step 3. Read the dataset of Mall_Customers csv file using Pandas library.

Step 4. From sklearn libraary select the cluster and import KMeans Clustering.

Step 5. Find the sum of squared distance between each points and the centroid in a cluster using Elbow Method.

Step 6. Plot the graph x and y as Number of Clusters and wcss respectively.

Step 7. Using the matplotlib library draw the scatter plot for the given number of clusters (ie. here n_clusters = 5).

Step 8. Stop the program.



## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: VESLIN ANISH A
RegisterNumber: 212223240175
*/
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wess = []
for i in range (1,11):
    kmeans = KMeans(n_clusters = i,init= "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wess.append(kmeans.inertia_)
plt.plot(range(1,11),wess)
plt.xlabel("No.of Clusters")
plt.ylabel("wess")
plt.title("Elbow Method")
km= KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"]= y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="orange",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="green",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
![Screenshot 2024-10-04 113903](https://github.com/user-attachments/assets/b898f2e2-13d8-4299-9407-190f973f89ac)
![Screenshot 2024-10-04 113924](https://github.com/user-attachments/assets/093ab659-7513-49d5-b31a-6306eb23e116)
![Screenshot 2024-10-04 114003](https://github.com/user-attachments/assets/6297d1bc-df73-4a25-a90b-c4a4eb9a757b)
![Screenshot 2024-10-04 114014](https://github.com/user-attachments/assets/98624174-ebb2-41d7-845c-d563d40a4561)
![Screenshot 2024-10-04 114024](https://github.com/user-attachments/assets/c89100e0-37e5-45d2-b50e-232f3ce57efa)










## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
