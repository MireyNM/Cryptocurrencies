# Cryptocurrencies

## Overview
Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. In this project, we are going to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

Since the data is not ideal, it will need to be processed to fit the machine learning models. Moreover, since there is no known output for what we are looking for, we have decided to use unsupervised learning and clustering algorithm. Finally, we will use data visualizations to share the findings. 

### Aim
The aim of this project is to create an analysis to find what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for a new investment..

## Resources 
- Data Source: <a href="https://github.com/MireyNM/Cryptocurrencies/blob/main/Crypto_Code/crypto_data.csv"> crypto_data.csv </a> </br>
- Software: Python 3.7.13, Jupyter Notebook </br>
- Scripts: <a href="https://github.com/MireyNM/Cryptocurrencies/blob/main/Crypto_Code/crypto_clustering.ipynb"> crypto_clustering.ipynb </a> </br>


## Analysis of Data 
### Preprocessing the Data 
As first step, we have loaded the data (Table 1) and we have preprocessed it to get the DataFrame of Table 2. 

<p align = "center">
<img width="499" alt="Outcomes_vs_Goals" src="https://user-images.githubusercontent.com/109363759/210882125-5f8e569e-de6b-4039-b628-3883b7f5c209.png">
</p>
<p align = "center">
Table 1 - DataFrame of original Data 
</p>


<p align = "center">
<img width="499" alt="Outcomes_vs_Goals" src="https://user-images.githubusercontent.com/109363759/210882183-d1c8dd25-92f5-4cfb-9a8b-33eec182868e.png">
</p>
<p align = "center">
Table 2 - Preprocessed DataFrame
</p>

### Reducing Data Dimensions Using PCA

 As a second step, we have applied the Principal Component Analysis (PCA) algorithm to reduce the dimensions of the DataFrame to three principal components and place these dimensions in a new DataFrame named ```pcs_df``` (Check Table 3) 

<p align = "center">
<img width="499" alt="Outcomes_vs_Goals" src="https://user-images.githubusercontent.com/109363759/210882920-a2d262e2-d9d5-4b93-9552-2b2a3dc8d054.png">
</p>
<p align = "center">
Table 3 - Reduced DataFrame (3 components)
</p>

### Clustering Cryptocurrencies Using K-means
As third step, we have:
- Used a K-means algorithm to create an elbow curve (Fig. 1) using ```hvplot``` to find the best value for K from the ```pcs_df``` DataFrame created in the second step. 
- Ran the K-means algorithm to predict the K clusters for the cryptocurrencies’ data and be able to create a new DataFrame including predicted clusters and cryptocurrencies features. This new DataFrame was named ```clustered_df``` (Table 4)


<p align = "center">
<img width="499" alt="Outcomes_vs_Goals" src="https://user-images.githubusercontent.com/109363759/210884482-90c64351-6aa1-40db-b708-d232170dd0af.png">
</p>
<p align = "center">
Fig. 1 - Elbow Curve 
</p>

<p align = "center">
<img width="499" alt="Outcomes_vs_Goals" src="https://user-images.githubusercontent.com/109363759/210887457-69c5b6a2-3c26-4c22-8d91-5894814a30d7.png">
</p>
<p align = "center">
Table 4-DataFrame including predicted clusters and cryptocurrencies features.
</p>


### Visualizing Cryptocurrencies Results 
In the last step we have: 
- Created scatter plots with Plotly Express and ```hvplot```, to visualize the distinct groups that correspond to the three principal components created in step 2. (See Fig. 2)
- Created a table with all the currently tradable cryptocurrencies ```hvplot.table()``` function (See Table 5)
- Scaled the data, created a new DataFrame that has the scaled data to create ```hvplot.scatter``` plot of ```TotalCoinsMined``` versus ```TotalCoinSupply``` by ```Class```. (See Fig. 3)

<p align = "center">
<img width="499" alt="Outcomes_vs_Goals" src="https://user-images.githubusercontent.com/109363759/210886761-53cc491b-1a07-4065-85c4-e7a63f126207.png">
</p>
<p align = "center">
Fig. 2- 3D scatter plot of the clusters. 
</p>

<p align = "center">
<img width="499" alt="Outcomes_vs_Goals" src="https://user-images.githubusercontent.com/109363759/210884888-76a899d2-84c1-4705-8c6d-00099dca1b6b.png">
</p>
<p align = "center">
Table 5- Table with all the currently tradable cryptocurrencies
</p>

<p align = "center">
<img width="499" alt="Outcomes_vs_Goals" src="https://user-images.githubusercontent.com/109363759/210886884-f4259df3-7959-497d-b7a1-2397737132e1.png">
</p>
<p align = "center">
Fig. 3 - 2D scatter plot of the clusters. 
</p>

