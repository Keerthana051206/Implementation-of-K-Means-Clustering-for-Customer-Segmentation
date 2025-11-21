# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import dataset and print head,info of the dataset
2.check for null values
3.Import kmeans and fit it to the dataset
4.Plot the graph using elbow method
5.Print the predicted array
6.Plot the customer segments

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: KEERTHANA C
RegisterNumber: 212224220047

*/
```
```
import pandas as pd
 import matplotlib.pyplot as plt
 data=pd.read_csv("/content/Mall_Customers (1).csv")
 data.head()
 data.info()
 data.isnull().sum()
 from sklearn.cluster import KMeans
 wcss=[]
 for i in range(1,11):
 kmeans=KMeans(n_clusters=i,init="k-means++")
 kmeans.fit(data.iloc[:,3:])
 wcss.append(kmeans.inertia_)
 plt.plot(range(1,11),wcss)
 plt.xlabel("No_of_Clusters")
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
 plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red"
 plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="blac
 plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue
 plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="gree
 plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="mage
 plt.legend()
 plt.title("Customer Segment")
```

## Output:
![K Means Clustering for Customer Segmentation](sam.png)
1.DATA HEAD():
<img width="647" height="221" alt="image" src="https://github.com/user-attachments/assets/d1c1d262-f42f-41a8-850f-47fbe7be6997" />
2.DATA INFO():
<img width="620" height="272" alt="image" src="https://github.com/user-attachments/assets/2cce42bb-98ac-4f1b-b523-39480c36dd93" />
3.DATA.ISNULL().SUM():
<img width="467" height="149" alt="image" src="https://github.com/user-attachments/assets/8bb0f789-9e92-4ea3-ae18-d08c69665255" />
4..PLOT USING ELBOW METHOD:
<img width="897" height="614" alt="image" src="https://github.com/user-attachments/assets/637dd832-7678-423c-94a3-6d7a576ead24" />
5.K-MEANS CLUSTERING:
<img width="880" height="237" alt="image" src="https://github.com/user-attachments/assets/8ce88248-26d6-47e8-9700-9cc05dde7440" />
6.Y_PRED ARRAY:
<img width="880" height="237" alt="image" src="https://github.com/user-attachments/assets/775c9341-e5b0-4b15-b5cd-caa460dbe0ce" />
7.CUSTOMER SEGMENT:
<img width="939" height="592" alt="image" src="https://github.com/user-attachments/assets/47dbda83-7ffb-4db6-ae31-edc3679506a6" />


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
