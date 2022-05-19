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
Before using data on unsupervised ML algorithms, the data has to cleaned properly in order to avoid any errors and to make sure we are getting the proper results. Needed to drop the null values and missing data, as well as an entire column if the data was not providing any valuable input (i.e. the data needs to be numerical). We also removed the duplicates, because they aren't providing anything new data and can skew the final data.

### Step 2: Feature Elimination, Feature Extraction & Reducing Data Dimensions Using PCA
When there is too many features in the dataset while working with unsupervised ML it can cause **overfitting**. To avoid this, we process out the reducing features known **dimensionality reduction**. There are two way to handle too many features: **elimination** and **extraction**. Elimination removes a lot of features so the model won't be run using every column. Extraction combines all features into a new data set that is ordered by how well the predicted varable is to the original variable. Principal component analysis, or PCA as it is better known, is a technique to speed up the algorithms when the input features are high.  It transforms a large variable set into a smaller set has most of the information from the original set.

### Step 3: Clustering Cryptocurrencies Using K-means and finding the Best Value using Elbow Curve
Clustering is a type of unsupervised learning that groups data points together. K-means is an unsupervised learning algorithm used to identify and solve issues that come up while clustering. Elbov curve is an easy method to determine the best number for K-means. The elbow curve requires two values to be created -  a list of K values and a list of inertia values. Inertia is one of the most common objective functions to use when creating an elbow curve. The inertia is measuring the amount of variation in the dataset. Inertia is the objective function to plot K values against.

### Step 4: Visualizing Cryptocurrencies Results and Interpretation 

Visualizing the clusters helps to graphically understand how they are arranged. 

**3D scatter plot** with **Plotly Express**. 
https://github.com/RabidZippers/Cryptocurrencies/blob/main/Cryptocurrencies/Resources/3D-Scatter(small).png

https://github.com/RabidZippers/Cryptocurrencies/blob/main/Cryptocurrencies/Resources/3D-Scatter(bigger).png

**2D visualization and correlation between Total Coins Supply and Total Coins Mined**

(https://github.com/RabidZippers/Cryptocurrencies/blob/main/Cryptocurrencies/Resources/Scatter%20Plot.png)

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



