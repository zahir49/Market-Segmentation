# Market-Segmentation

1.	It means aggregating customers into groups or segments with common needs and who respond similarly to a marketing action.
2.	It helps companies to define and better understand their target audiences and ideal customers.
3.	For ex, if I am a marketer, segmentation will allow me to identify the right market for my products and then I can target my marketing more effectively.
Understanding the data:
1.	For this project, I had taken a dataset which contains information about 9000 credit card holders with 18 behavioural columns. 
2.	The aim is to segment them into different clusters so that we can give them recommendations (like saving plans, loans and wealth management) based on their interest.
3.	Now, after understanding what we are going to do, we will start with data pre-processing, then we will do Exploratory Data analysis and finally we will build a model to classify customers into different clusters.
4.	Starting with the project, I had imported the required libraries like numpy, pandas, matplotlib, seaborn and sklearn.
5.	Then, I had loaded the dataset into a pandas dataframe and had a look at the dataframe to understand the data. 
6.	I checked the shape of the data. It had 8950 entries and 18 columns.
Data Pre-Processing:
1.	I dropped the column ‘customer_id’ as it has no significance.
2.	Then I checked if the dataframe has any missing values with isnull().sum(). I found 2 columns had missing values. So, I filled the missing values with their respective column mean.
3.	I also checked for duplicate entries and found no duplicates.
Exploratory Data Analysis:
1.	I used describe function to know the descriptive statistics of the data.
2.	Then I plotted KDE Plot (Kernel Density Estimator) of each column.
3.	I also plotted a heatmap to see the correlation between each and every column.
Model Building:
1.	Before building the model, I had to scale the data because some values were small and some were large and this would make the model predict wrongly.
(scaled the data using standardScaler from sklearn.preprocessing)
2.	I also had to reduce the dimensionality so that I can use the data for cluster visualization.
I used PCA (Principal Component Analysis) for this purpose and stored the data to a variable.
3.	For model building I decided to use KMeans Algorithm. It is an unsupervised ML Algorithm.
4.	To use KMeans, first, we need to find the optimal K value. Where, K is the no of clusters. This can be done by using Elbow Method. 
5.	In Elbow Method, we plot WCSS (within cluster sum of squares) w.r.t k values. The optimal k value is the value of k where there is an elbow shape in the graph. The value of k found was 4.
6.	Then I created an object of KMeans	and called the fit_predict function on the scaled dataframe to fit the data to the model.
7.	Then I concatenated the PCA data with predicted cluster labels data and used a scatter plot to visualize the cluster dataframe.
8.	Then I found the cluster centres and transformed the dataframe to original form using inverse_transform function.
9.	I added a cluster column which contains the cluster no for each data entries and plotted a countplot of cluster. Cluster 2 has the max customers.
Conclusions:
1.	I plotted histogram of each column of dataframe w.r.t. clusters. To see their relation with each cluster.

