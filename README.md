# Customer Loyalty Program for E-Commerce


</b> Project to identify the profile of the most valuable customers, for the construction of a loyalty program.
<br>

<div align="center">
<img src="https://user-images.githubusercontent.com/87071331/215501100-72dd6033-fd1d-421c-9dae-bd7ca0c6fbaf.jpg" width="500px" />
</div>

#### Segmentation of High Value Customers - Loyalty Program
# 1. Business problem.
* The All-in-One-Place company is an online retail store based in the United Kingdom and captured the sales data of different products in the period of one year (November 2016 to December 2017).

* In just one year of operation, the marketing team realized that some customers buy more expensive products with high frequency and contribute a significant portion of the company's revenue.

* As a result, the marketing team will launch a loyalty program for the best customers in the company's database, called High Value Customers - Champions. However, the team does not have advanced data analysis skills to select program participants.

* For this reason, the marketing team asked me, as a data scientist, to select eligible customers for this loyalty program using advanced modeling and data manipulation techniques.

## 1.2 Purpose
Group more than 5000 customers into groups by consumption profile, and identify the most valuable customers.

In addition, the following business questions must be answered by the marketing area:

- Who are eligible to participate in the Loyals program?
- How many customers will be part of the group?
- What are the main characteristics of these customers?
- What is the percentage of revenue contribution coming from Loyals?
- What is this group's revenue expectation for the coming months?
- What are the conditions for a person to be eligible for Loyals?
- What are the conditions for a person to be removed from Loyals?
- What is the guarantee that the Loyals program is better than the rest of the base?
- What actions can the marketing team take to increase revenue?

# 2. Business assumptions
The marketing team needs to visualize the profiles of each group of customers within the Metabase visualization tool, already used by the company.

# 3. Solution planning

## 3.1. Final product
What will actually be delivered?

A dataframe with the cluster data

## 3.2. Tools
What tools will be used in the process?
  - Python 3.8.0;
  - Jupyter Notebook;
  - Git e Github;
  - Sweetviz;
  - Clustering Algorithms;
  - Embedding techniques;
# 3.3 Process
## 3.3.1 Solution strategy
Based on the objective of the project, it is a clustering project (grouping).
My strategy for solving this challenge, based on the CRISP-DS methodology, is detailed by the plan below:

# Solution Planning
Solution planning, considering the business context.
## Date Description:
  - Collect data on AWS EC2.
  - Understand the meaning of each stakeholder attribute.
  - Rename columns, understand dimensions and data types.
  - Identify and handle null data.
  - Standardize data types.
  - Analyze attributes through descriptive statistics.
## Data Filtering:
  - Filter data according to descriptive statistics analysis.

## Feature Engineering:
  - Change the granularity of the data from the invoice issued to the customer.
  - Create features at client granularity.
## Exploratory Data Analysis I:
  - Perform a univariate analysis using Pandas Profiling to:
  - Analyze variables with high variability, candidates for model input.
  - Analyze inconsistent outliers in order to filter them in the next cycles.
  - Perform a bivariate analysis, visually identifying variables without variability.
## RFM Analysis
  - RFM Analysis is a scientifically controlled marketing method used to group your company's customers based on purchasing behavior, measuring and analyzing consumption habits in terms of Frequency, Recency and Monetary.
  
## Data Preparation:
  - Apply transformations to features, facilitating model learning.

## Feature Selection:
  - Select the features with greater variability, aiming to improve the performance of the models.
  - Analyze the result in conjunction with the analysis performed on the EDA.

### study of Space:
  - Carry out a study of the data space, seeking a more organized space with embedding.

## Hyperparameter Fine Tuning:
  - Experimentation of clustering models with different Ks (number of groups), in the feature space and in the embedding space.
  - Fine-tune hyperparameters in each model, identifying the best set of parameters to maximize its learnability.
  - Performance comparison of models with SS Score in each space.
  - Choose the best model and number of groups, considering performance and ease of decision-making for the business.
  - Perform silhouette analysis to verify the quality of clustering.
  
## Machine Learning Modeling:
  - Run the chosen algorithm with chosen parameters and number of K, in the chosen data space.
  - Confirm performance with SS Score.
  - Convert Model Performance to Business Values.
  
## Answer business questions
  - Answer business questions
  
## Business Performance
  - Plot results translating to the business team.
  
# 4. Top 3 data insights
During the exploratory data analysis, insights were generated for the business team, through the validation of hypotheses.

Insights are new information, or information that contradicts previously established beliefs of the business team. They are also actionable, enabling action to drive future results.

**H1 - Loyals cluster customers have an average of unique products purchased above 10% of total purchases.**

True: 50% of unique product volume came from the Loyals cluster.

Business insight: Apply marketing strategies to offer similar products to other clusters, based on those purchased by Loyals, aiming to reduce the distance between both in this regard.

**H2 - Loyals cluster customers have an average number of returns 10% below the average of the total customer base.**

False: The Insider cluster has an average number of bounces that are 256% higher than the average for the total customer base.

Business insight: Given the number of returns well above expectations, carry out a detailed survey of reverse logistics costs with the responsible area, assessing the negative impact against the other positive characteristics of Loyals.

**H3 - The median revenue of the Loyals cluster is 10% higher than the median revenue of all clusters.**
True: The median revenue of the Loyals cluster is 155% (1.5x) greater than the median revenue of all clusters.

Business insight: Allocate a dedicated team in the marketing area to take care of the relationship with Loyals, given the representativeness of revenue within the company, in relation to the business.

# 5. Applied Machine Learning Models
  Four clustering models were applied: K-Means, GMM (Gaussian Mixture Model), HC (Hierarchical Clustering) and DBScan.
  
  The 4 models were tested considering 2 to 12 possible groups of customers (k). Above 12 would make the work of the marketing team more difficult.
  
  These tests were performed both in the feature space (original data space) and in the embedding space.
  
  The algorithms used to create the embedding spaces were: PCA, UMAP, t-SNE and an embedding based on trees with Random Forest.

# 6. Performance of the Machine Learning model
The performance of the models was measured using the SS (Silhouette Score) metric, as it is applicable to all tested clustering models.

The best result was obtained with the K-Means, with k=8, in the embedding space generated by UMAP, with SS = 0.64, this was the chosen model to deploy in production.

# 7. Business Results
Business questions were answered within the Jupyter Notebook, in cycle 8.

Regarding financial results, we start from the fact that the median revenue of the Loyals cluster is (2,78x) greater than the median revenue of all clusters, as already explained.

With the premise that the Stand Out Brands marketing team, through the project, will increase the number of Loyals by 10% next year, we will have a median increase of 2,78 x in revenue in 10% of the base.

The number of Loyals customers in the last year (373 days) is: 478. The expected number of Loyals customers for the next year is: 1965. We will therefore have 47 new customers.

Assuming the same median revenue per Loyal, the expected revenue increment is $192.075.

# 8. Conclusions
Based on the business results, it is concluded that the project objective was achieved.

With the data solution delivered, Stand Out Brands now has a robust and profitable loyalty program.

Marketing actions aimed at other groups of customers can also be carried out, further increasing the scope of the work carried out.

# 9. Future improvements
  - Create more features from existing ones, seeking to generate more inputs for learning the models.

 



