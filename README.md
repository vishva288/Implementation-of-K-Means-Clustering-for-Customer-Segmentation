# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Load the customer dataset and select relevant features such as Annual Income and Spending Score.
2.Determine the optimal number of clusters using the Elbow Method by computing WCSS for different values of k.
3.Initialize the K-Means algorithm with the chosen number of clusters and fit it to the dataset.
4.Assign each customer to the nearest cluster centroid based on distance.
5.Visualize the formed clusters to analyze and interpret customer segments.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Vishva S
RegisterNumber:  
*/
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

data = pd.read_csv("/content/Mall_Customers.csv")

print(data.head())

print(data.info())

print(data.isnull().sum())

wcss = []

for i in range(1, 11):
    kmeans = KMeans(n_clusters=i, init="k-means++", random_state=42)
    kmeans.fit(data.iloc[:, 3:5])   
    wcss.append(kmeans.inertia_)

plt.plot(range(1, 11), wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("WCSS")
plt.title("Elbow Method")
plt.show()

km = KMeans(n_clusters=5, init="k-means++", random_state=42)
km.fit(data.iloc[:, 3:5])

y_pred = km.predict(data.iloc[:, 3:5])

data["cluster"] = y_pred

df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]

plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"], c="red", label="Cluster 0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"], c="black", label="Cluster 1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"], c="blue", label="Cluster 2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"], c="green", label="Cluster 3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"], c="magenta", label="Cluster 4")

plt.xlabel("Annual Income (k$)")
plt.ylabel("Spending Score (1-100)")
plt.title("Customer Segments")
plt.legend()
plt.show()
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

data = pd.read_csv("/content/Mall_Customers.csv")

print(data.head())

print(data.info())

print(data.isnull().sum())

wcss = []

for i in range(1, 11):
    kmeans = KMeans(n_clusters=i, init="k-means++", random_state=42)
    kmeans.fit(data.iloc[:, 3:5])   
    wcss.append(kmeans.inertia_)

plt.plot(range(1, 11), wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("WCSS")
plt.title("Elbow Method")
plt.show()

km = KMeans(n_clusters=5, init="k-means++", random_state=42)
km.fit(data.iloc[:, 3:5])

y_pred = km.predict(data.iloc[:, 3:5])

data["cluster"] = y_pred

df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]

plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"], c="red", label="Cluster 0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"], c="black", label="Cluster 1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"], c="blue", label="Cluster 2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"], c="green", label="Cluster 3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"], c="magenta", label="Cluster 4")

plt.xlabel("Annual Income (k$)")
plt.ylabel("Spending Score (1-100)")
plt.title("Customer Segments")
plt.legend()
plt.show()

```

## Output:
<img width="960" height="635" alt="Screenshot 2026-03-09 103538" src="https://github.com/user-attachments/assets/eb05f4da-0fa9-4008-9660-e4411de294b2" />
<img width="833" height="490" alt="Screenshot 2026-03-09 103546" src="https://github.com/user-attachments/assets/80834965-92a4-486e-8168-907cf53e5ca1" />



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
