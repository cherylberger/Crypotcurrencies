# Crypotcurrencies
Cheryl Berger
Module 18 - Data Analytics

## Overview:
Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. This analysis will be used to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

## Resources
Code- https://github.com/cherylberger/Crypotcurrencies/blob/main/crypto_clustering.ipynb
Data- https://github.com/cherylberger/Crypotcurrencies/blob/main/Resources/crypto_data.csv
## Results:

### Deliverable 1: Preprocess the Data for PCA
![image](https://user-images.githubusercontent.com/94234511/161364398-428a6863-33ed-4491-884a-381b58d17741.png)
-Keep all the cryptocurrencies that are being traded & the alogrithms that are working
-Sort the data to see if there are any algorithms that are not working
-Find & Remove rows that have at least 1 null value.
- Keep the rows where coins are mined bit drop the IsTraded column from the data
![image](https://user-images.githubusercontent.com/94234511/161364642-40d2eb97-5e1e-455a-8b25-e1c683cf92a3.png)

- Create a new DataFrame that holds only the cryptocurrencies names.
![image](https://user-images.githubusercontent.com/94234511/161364754-71a02f9b-88df-4302-a787-d420f11c7ca2.png)
-Drop the 'CoinName' column since it's not going to be used on the clustering algorithm.
-Use get_dummies() to create variables for text features.
![image](https://user-images.githubusercontent.com/94234511/161364854-a02e36c5-dc48-4e61-9dec-6176ea9c2a76.png)
- Scale the data using Standard Scaler
### Deliverable 2: Reduce the Data Dimensions Using PCA
-Use PCA to reduce dimension to three principal components.
-Fit the model
-Create a DataFrame with the three principal components.
![image](https://user-images.githubusercontent.com/94234511/161364936-c5fb075c-0bfc-4922-b962-0a2481e25ada.png)

### Deliverable 3: Cluster Crytocurrencies Using K-Means¶
-Find the Best Value for k Using the Elbow Curve
inertia = []
k = list(range(1, 11))

-Run K-Means with k=4
for i in k:
    km = KMeans(n_clusters=i, random_state=0)

    # Fit the model
    km.fit(X_pca)
    inertia.append(km.inertia_)
-Create the elbow curve
![image](https://user-images.githubusercontent.com/94234511/161365013-c74bb7ac-7ea1-481f-88af-e3c19b6dd78a.png)
- Initialize the K means model, fit the data and run the predictions
![image](https://user-images.githubusercontent.com/94234511/161365032-56ae31dd-cd37-4414-9657-344d0429c6b1.png)
-Create a new DataFrame including predicted clusters and cryptocurrencies features.
![image](https://user-images.githubusercontent.com/94234511/161365094-bb66ef6d-6f0f-49b6-bb08-e3c8cff38ea4.png)

### Deliverable 4: Visualizing Cryptocurrencies Results
- Create the 3D-Scatter with Clusters
![image](https://user-images.githubusercontent.com/94234511/161365163-26405f00-82aa-4db6-af66-bdc4b0880b95.png)
-Create a datatable with the Tradeable currencies
![image](https://user-images.githubusercontent.com/94234511/161365174-48c11457-7445-4a06-9b7b-c67d8a3444b3.png)
-Create a new DataFrame that has the scaled data with the clustered_df DataFrame index.
![image](https://user-images.githubusercontent.com/94234511/161364297-86120cc9-d3f1-4849-8a3a-10c2b986803d.png)
- Plot the results 
![image](https://user-images.githubusercontent.com/94234511/161365237-70127f38-7dac-4d04-8ddb-5e02c96061ae.png)

