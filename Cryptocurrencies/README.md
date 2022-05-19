# Cryptocurrencies

## Project Overview
This project uses **unsupervised machine learning** on cryptocurrency data. The purpose is to create a report that includes what cryptocurrencies are on the trading market and how to create a system for potential investments into cryptocurrency.

## Resources
- Software: **Jupyter Notebook**
- Languages: **Python**
- Libraries: **Scikit-learn**, **Pandas**, **Plotly**
- Environment: **Python 3.7**
- Data Source: [crypto_data.csv](Data\crypto_data.csv)

## Procedure and Results
In order to use unsupervised machine learning models on the data, the data needs to be processed in order to fit the machine learning models. There is no known output and the unsupervised ML is ideal for that type of analysis. 

### Step 1: Preprocessing the Data
Before using data on unsupervised ML algorithms, the data has to preprocessed properly in order to avoid any errors and to ensure we are getting the right results. These steps include **data selection** (what data is available, what data is missing, and what data can be removed), **data processing** (organizing the data by formatting, cleaning, and sampling) and **data transformation** (transforming data into a simpler format for storage and future use, such as a CSV, spreadsheet, or database file). 

Requirements for dataset:

:round_pushpin:	**Null values and missing data:** Unsupervised learning models can't handle null values or missing data. Drop null or missing values or make a decision and drop the entire column. 

:round_pushpin:	**Datatype:** All data has to be converted to numerical data type. 

:round_pushpin:	**Duplicates:** Remove duplicates, they aren’t telling us anything new and can screw the results.

:round_pushpin:	**Scaled values:** Data has been manipulated to ensure that the variance between the numbers won't skew results. When features have different scales, they can have a disproportionate impact on the model. The unscaled value could lead to messy graphs. Therefore, it is important to understand when to scale and normalize data. For example, if four columns of data are single digits, and the fifth column is in the millions, we would need to scale the fifth column to align the other four (1). 

### Step 2: Feature Elimination, Feature Extraction & Reducing Data Dimensions Using PCA
Having too many features in the dataset when working with unsupervised ML can cause **overfitting**. To avoid this, we can use process of reducing features also known as **dimensionality reduction**. There are two options for coping with too many features: **elimination** and **extraction**.

:round_pushpin: **Feature elimination** removes a good amount of features so the model won't be run using every column.

:round_pushpin: **Feature extraction** combines all features into a new set that is ordered by how well they predict our original variable.

:round_pushpin: **PCA** is a statistical technique to speed up machine learning algorithms when the number of input features (or dimensions) is too high. PCA reduces the number of dimensions by transforming a large set of variables into a smaller one that contains most of the information in the original large set (2).

The first step in PCA is to standardize these features by using the `StandardScaler` library. After the data has been standardized use PCA to reduce the number of features (argument of `n_components`) in order to get a smaller set of dimensions called ***principal components***. These new components are new main dimensions of variation that contain most of the information in the original dataset (2).

`explained_variance_ratio` tells how much information can be attributed to each principal component: for example the first principal component contains 72.77% of the variance and the second contains 23.03%. Together, they contain 95.80% of the information (2).

### Step 3: Clustering Cryptocurrencies Using K-means and finding the Best Value using Elbow Curve

:round_pushpin: **Clustering** is a type of unsupervised learning that groups data points together (3). 

:round_pushpin: **K-means** is an unsupervised learning algorithm used to identify and solve clustering issues. K represents how many clusters there will be. These clusters are then determined by the means of all the points that will belong to the cluster. The K-means algorithm groups the data into K clusters, where belonging to a cluster is based on some similarity or distance measure to a centroid. The centroid is found by taking the mean of all the x values in a cluster, and the mean of all the y values in a cluster (4).

:round_pushpin: **Elbov curve** is an easy method for determining the best number for K-means. To create the elbow curve, two values are needed -  a list of K values and a list of inertia values. Loop through 10 values for K, for example and determine the inertia: `range (1, 11)` (5).

:round_pushpin: **Inertia** is one of the most common objective functions to use when creating an elbow curve. The inertia is measuring the amount of variation in the dataset. Inertia is the objective function to plot K values against (5). 

### Step 4: Visualizing Cryptocurrencies Results and Interpretation 

Visualizing the clusters helps to graphically understand how they are arranged. 

**3D graph and PCA visualization**

For 3D visualization I used **3D scatter plot** with **Plotly Express**. 3 principal components (on x, y and z axis), that were created with PCA algorithm are plotted on the graph.  These 3 components contains most of the information in the original large set. As we can see form the graph, cryptocurrency is clustered in 4 groups with similar characteristics. When hover over the specific element the graph shows label with Coin Name and its Algorithm. 

<p align="center">
<img src="Graphics/3D.PNG" width="60%" height="60%">
</p>
<p align="center">
<i>Figure 1: Cryptocurrencies clustered in 4 main groups.</i>
</p>

**2D visualization and correlation between Total Coins Supply and Total Coins Mined**

For 2D visualization I used **hvPlot**, a graphing library that allows deeper exploration of the data. This graph has Total Coins Supply on y-axis and Total Coins Mined on x-axis. From the graph we can see correlation between those two components. Different colors indicate different classes that crypto coins belong to. When hover over the specific element the graph shows label with Coin Name and its Class.

<p align="center">
<img src="Graphics/2D.PNG" width="60%" height="60%">
</p>
<p align="center">
<i>Figure 2: Correlation between Total Coins Supply and Total Coins Mined.</i>
</p>

**Interactive Table**

To create interactive table, I used **hvplot library**. When clicked on the header, the values in that columns are sorted. This interactive table is ideal to see what tradable coins are on the market, algorithms used and can be easily sorted by in ascending or descending order.

<p align="center">
<img src="Graphics/Table.PNG" width="60%" height="60%">
</p>
<p align="center">
<i>Figure 3: Interactive table of tradable crypto coins.</i>
</p>

## References
-	(1) Module 18.2.5 Data Processing https://courses.bootcampspot.com/courses/200/pages/18-dot-2-5-data-processing?module_item_id=104383, Trilogy Education Services, 2000. Web 12 Nov 2020.
-	(2) Module 18.5.2 Principal Component Analysis https://courses.bootcampspot.com/courses/200/pages/18-dot-5-2-principal-component-analysis?module_item_id=104394, Trilogy Education Services, 2000. Web 12 Nov 2020.
-	(3) Module 18.3.1 Clustering Data https://courses.bootcampspot.com/courses/200/pages/18-dot-3-1-clustering-data?module_item_id=104386
-	(4) Module 18.3.2 K-means Algorithm, Trilogy Education Services, 2000. Web 12 Nov 2020.
https://courses.bootcampspot.com/courses/200/pages/18-dot-3-2-k-means-algorithm?module_item_id=104387, Trilogy Education Services, 2000. Web 12 Nov 2020.
-	(5) Module 18.4.1 Elbow Curve https://courses.bootcampspot.com/courses/200/pages/18-dot-4-1-elbow-curve?module_item_id=104390, Trilogy Education Services, 2000. Web 12 Nov 2020.



