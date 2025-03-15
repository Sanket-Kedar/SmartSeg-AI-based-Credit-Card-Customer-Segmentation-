<h1>SmartSeg-AI-based-Credit-Card-Customer-Segmentation</h1>

<h2>Problem Statement</h2>

Traditional approaches often fall missing in detecting invisible trends, which leads to incomplete financial product and marketing strategy customization. By using unsupervised machine learning methods like K-Means Clustering, Hierarchical Clustering, and DBSCAN to examine transaction data and find hidden customer groups, SmartSeg seeks to overcome these issues. These insights enable companies to improve client engagement, optimize products, and anticipate turnover. Explainable AI (XAI) is integrated into the project to ensure usability and confidence, allowing stakeholders to analyze the findings and make wise decisions. In the cutthroat financial sector, SmartSeg aims to revolutionize customer relationship management by offering a scalable and data-driven strategy, resulting in increased satisfaction and business outcomes.


<h2>Dataset Description</h2>

dataset link : <a href="https://www.kaggle.com/datasets/arjunbhasin2013/ccdata" >credit card dataset </a>

The dataset is procured from Kaggle.

The dataset contains information from around 8,950 active credit card holders and reflects their behavioral trends over the past six months. 

Each entry corresponds to an individual customer and features 18 unique behavioral variables, allowing for an in-depth examination of credit card utilization patterns and customer segmentation.

The 18 unique behavioral variables are listed in the following section:

(1) CUST_ID: A categorical variable representing the unique identification of each credit card holder. 

(2) BALANCE: This variable signifies the balance amount remaining in the account available for making purchases. 

(3) BALANCE_FREQUENCY: A continuous variable measuring the frequency with which the account balance is updated. It is scored between 0 and 1, with 1 indicating frequent updates and 0 indicating infrequent updates

(4) PURCHASES: This variable represents the total amount of purchases made from the credit card account

(5) ONEOFF_PURCHASES: Indicates the maximum purchase amount made in a single transaction. 

(6) INSTALLMENTS_PURCHASES: The amount of purchases made in installments. 

(7) CASH_ADVANCE: Represents cash advances taken by the cardholder. 

(8) PURCHASES_FREQUENCY: This variable quantifies the frequency of purchase transactions, with a score between 0 and 1, where 1 indicates frequent purchases and 0 indicates infrequent purchases. 

(9) ONEOFFPURCHASESFREQUENCY: Measures the frequency of purchases made in one go (i.e., single transactions), with a score of 1 indicating frequent occurrences and 0 indicating infrequent occurrences. 

(10) PURCHASESINSTALLMENTSFREQUENCY: Reflects how often purchases are made in installments, with 1 denoting frequent installment purchases and 0 indicating infrequent installment purchases. 

(11) CASHADVANCEFREQUENCY: Measures the frequency of cash advances being taken by the cardholder. 

(12) CASHADVANCETRX: The number of transactions involving "Cash in Advance." 

(13) PURCHASES_TRX: Represents the number of purchase transactions made using the credit card. 

(14) CREDIT_LIMIT: Denotes the credit limit assigned to the user for the credit card. 

(15) PAYMENTS: This signifies the total amount of payments made by the user. 

(16) MINIMUM_PAYMENTS: Represents the minimum amount of payments made by the user. 

(17) PRCFULLPAYMENT: Indicates the percentage of the full credit card balance paid by the user. 

(18) TENURE: Reflects the tenure of the credit card service for the user. 


<h2>System Architecture </h2>

![Screenshot 2025-03-15 102650](https://github.com/user-attachments/assets/22d1d8a2-27bc-48aa-afb3-9526e1f5915e)

<h2>Results</h2>

Evaluating an optimal number of clusters using the elbow method:

![Screenshot 2025-03-15 105219](https://github.com/user-attachments/assets/bb234ff5-3612-41ec-aad9-047ea0d956f9)

The above Fig shows the elbow plot for K-means clustering. The distortion scores fall drastically till k=4, that is, the optimal clusters, then become flat henceforth. The dashed black line marks the elbow point, where the score is approximately 24519. The fit times for each k are shown on a green dashed line.

![Screenshot 2025-03-15 105158](https://github.com/user-attachments/assets/851a3dea-17c4-4f02-990d-bed50c7f85c8)

The above Fig shows the plot that depicts the Calinski-Harabasz scores for a K-means cluster of different k values. Here we can clearly see that until k=4, the score rapidly increases. For k values beyond this, the scores start to fluctuate, indicating that k=4 is the optimal number of clusters.

![Screenshot 2025-03-15 105233](https://github.com/user-attachments/assets/ba8796ea-9453-45ff-ad6d-d530dd78c9ec)

The above scatter plot visualizes k-means clustering using two principal components. The data points have been clustered into four clusters differentiated by colors, and their centroids are shown by red circles. The clustering shows distinct separations, highlighting the effectiveness of the model.

![Screenshot 2025-03-15 105244](https://github.com/user-attachments/assets/abc306c1-dff7-4ded-8065-075284e22199)

The above scatterplot displays the results of a DBSCAN clustering algorithm, with points plotted along two principal components derived using PCA. Data points are assigned to clusters, represented by teal and yellow colors while noise points are shown in purple. The plot illustrates how DBSCAN identifies clusters of varying densities.

![Screenshot 2025-03-15 105255](https://github.com/user-attachments/assets/2988b0a1-013a-4927-afb4-9add9f656816)

Fig displays the result of hierarchical clustering projected into a two-dimensional plane by PCA. Data points are colored according to the cluster they were assigned to, such as green, yellow, purple, and blue. Hierarchical clustering has organized the data into densely populated clusters while capturing the underlying structure of the dataset.

![Screenshot 2025-03-15 105306](https://github.com/user-attachments/assets/9c7ad981-0f6c-4c80-9a2e-570107739068)

Fig shows the result of the spectral clustering algorithm. Points are assigned to different clusters with purple, yellow, green, and blue colors. Clustering reveals how distinct the data separation has been done by an algorithm into coherent groups, the quality of clusters, and how isolated points mark the difference in density and spatial distribution. 

![Screenshot 2025-03-15 105316](https://github.com/user-attachments/assets/1f181d7d-44d4-4640-98f1-1452483323c0)

In summary, it can be inferred that K-Means exhibits the highest clustering quality of the three algorithms, as evidenced by its lowest Davies-Bouldin index and slightly improved overlap of clusters when compared to hierarchical clustering.

![Screenshot 2025-03-15 105330](https://github.com/user-attachments/assets/718a8a0e-891f-44fb-b726-763d0e4a0647)

Above fig shows Clustering results for K-Means based on the mean matrix.

<img width="704" alt="image" src="https://github.com/user-attachments/assets/d2c1f374-20e0-49ad-9a05-07c2e47aa34a" />

Fig gives insight into which features are most impactful within the model's predictions—specifically, "BALANCE_FREQUENCY" and "BALANCE." For "BALANCE_FREQUENCY," higher values colored red mostly increased the model's prediction due to the positive SHAP value output, while the lower ones have a smaller impact, colored blue. 

![Screenshot 2025-03-15 105417](https://github.com/user-attachments/assets/627899cd-f71b-45ec-98dd-a4b36d31088f)

Fig shows the predicted probabilities and feature contributions for Cluster 1 and Cluster 2 according to a clustering model. The prediction probabilities are identical between the two clusters, with Cluster 2 being the most likely assigned cluster at 0.59 and Cluster 1 being the second most likely at 0.22. Feature thresholds drive the decision-making in assigning Cluster 2: "BALANCE ≤ -1.49" contributes highly to the prediction, with a value of 0.21, whereas "-1.26 < BALANCE_FREQUENCY" adds contributions of smaller values, ranging between 0.07 and 0.08. These values are constant across the clusters for "BALANCE = -1.68" and "BALANCE_FREQUENCY = -1.08." Therefore, it seems from this that both features are relevant for cluster assignments, but "BALANCE" is driving the model more.
