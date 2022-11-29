# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program.
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: 212221230068
RegisterNumber: NAVEENKUMAR V  
*/
```
~~~
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
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="yellow",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="pink",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="purple",label="cluster4")
plt.legend()
plt.title("Customer Segments")
~~~

## Output:
![K Means Clustering for Customer Segmentation](sam.png)
![204441690-660e5815-98a5-4d85-9350-adedd04f4cd4](https://user-images.githubusercontent.com/94165322/204450619-cffbb3b6-91de-4fd6-8170-9de06363237a.png)
![204441720-b5888405-402a-4803-93b1-4cb18770d34d](https://user-images.githubusercontent.com/94165322/204450658-00a9f80b-1f85-447a-9feb-6956a7a1ce6f.png)
![204441760-48851371-d136-4594-90a3-01df862022f9](https://user-images.githubusercontent.com/94165322/204450698-094aff2e-11d8-4d24-bdd6-d205e400930a.png)
![204441799-c1a41243-ef51-400a-b371-60f72df4a7d2](https://user-images.githubusercontent.com/94165322/204450776-fc53eda7-651c-4e9f-b217-4985401616b5.png)
![204441847-dc2d4c2b-fee6-43a9-a6fc-091b608be680](https://user-images.githubusercontent.com/94165322/204450824-d3badb40-93d6-4a22-ba8f-d30d3556dfeb.png)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
