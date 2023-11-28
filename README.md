I. Introduction
This project contains an eCommerce dataset that I will explore using SQL on Google BigQuery. The dataset is based on the Google Analytics public dataset and contains data from an eCommerce website.

II. Requirements
Google Cloud Platform account
Project on Google Cloud Platform
Google BigQuery API enabled
SQL query editor or IDE
III. Dataset Access
The eCommerce dataset is stored in a public Google BigQuery dataset. To access the dataset, follow these steps:

Log in to your Google Cloud Platform account and create a new project.
Navigate to the BigQuery console and select your newly created project.
In the navigation panel, select "Add Data" and then "Search a project".
Enter the project ID "bigquery-public-data.google_analytics_sample.ga_sessions" and click "Enter".
Click on the "ga_sessions_" table to open it.
IV. Exploring the Dataset
In this project, I will write 08 query in Bigquery base on Google Analytics dataset

Query 01: Calculate total visit, pageview, transaction and revenue for January, February and March 2017 order by month
SQL code
image

Query results
image

Query 02: Bounce rate per traffic source in July 2017
SQL code
image

Query results
image

Query 3: Revenue by traffic source by week, by month in June 2017
SQL code
image

Query results
image

Query 04: Average number of product pageviews by purchaser type (purchasers vs non-purchasers) in June, July 2017
SQL code
image

Query results
image

Query 05: Average number of transactions per user that made a purchase in July 2017
SQL code
image

Query results
image

Query 06: Average amount of money spent per session. Only include purchaser data in July 2017
SQL code
image

Query results
image

Query 07: Other products purchased by customers who purchased product "YouTube Men's Vintage Henley" in July 2017. Output should show product name and the quantity was ordered.
SQL code
image

Query results
image

Query 08: Calculate cohort map from pageview to addtocart to purchase in last 3 month.
SQL code
with get_1month_cohort as (SELECT  
  CASE WHEN 1 = 1 THEN "201701" END AS month,
  COUNT(CASE WHEN hits.eCommerceAction.action_type = "2" AND product.isImpression IS NULL THEN fullVisitorId END) AS 
num_product_view,
  COUNT(CASE WHEN hits.eCommerceAction.action_type = "3" AND product.isImpression IS NULL THEN fullVisitorId END) AS 
num_addtocart,
  COUNT(CASE WHEN hits.eCommerceAction.action_type = "6" AND product.isImpression IS NULL THEN fullVisitorId END) AS 
num_purchase,
FROM `bigquery-public-data.google_analytics_sample.ga_sessions_201701*` ,
UNNEST(hits) as hits,
UNNEST(hits.product) as product),

get_2month_cohort as (SELECT  
  CASE WHEN 1 = 1 THEN "201702" END AS month,
  COUNT(CASE WHEN hits.eCommerceAction.action_type = "2" AND product.isImpression IS NULL THEN fullVisitorId END) AS 
num_product_view,
  COUNT(CASE WHEN hits.eCommerceAction.action_type = "3" AND product.isImpression IS NULL THEN fullVisitorId END) AS 
num_addtocart,
  COUNT(CASE WHEN hits.eCommerceAction.action_type = "6" AND product.isImpression IS NULL THEN fullVisitorId END) AS 
num_purchase,
FROM `bigquery-public-data.google_analytics_sample.ga_sessions_201702*` ,
UNNEST(hits) as hits,
UNNEST(hits.product) as product),

get_3month_cohort as (SELECT  
  CASE WHEN 1 = 1 THEN "201703" END AS month,
  COUNT(CASE WHEN hits.eCommerceAction.action_type = "2" AND product.isImpression IS NULL THEN fullVisitorId END) AS 
num_product_view,
  COUNT(CASE WHEN hits.eCommerceAction.action_type = "3" AND product.isImpression IS NULL THEN fullVisitorId END) AS 
num_addtocart,
  COUNT(CASE WHEN hits.eCommerceAction.action_type = "6" AND product.isImpression IS NULL THEN fullVisitorId END) AS 
num_purchase,
FROM `bigquery-public-data.google_analytics_sample.ga_sessions_201703*` ,
UNNEST(hits) as hits,
UNNEST(hits.product) as product)

select 
month,
num_product_view,
num_addtocart,
num_purchase,
ROUND(num_addtocart/num_product_view*100,2) as add_to_cart_rate,
ROUND(num_purchase/num_product_view*100,2) as purchase_rate
from 
(SELECT * FROM get_1month_cohort
UNION ALL 
SELECT * FROM get_2month_cohort
UNION ALL
SELECT * FROM get_3month_cohort)
ORDER BY month;
Query results
image

V. Conclusion
In conclusion, my exploration of the eCommerce dataset using SQL on Google BigQuery based on the Google Analytics dataset has revealed several interesting insights.
By exploring eCommerce dataset, I have gained valuable information about total visits, pageview, transactions, bounce rate, and revenue per traffic source,.... which could inform future business decisions.
To deep dive into the insights and key trends, the next step will visualize the data with some software like Power BI,Tableau,...
Overall, this project has demonstrated the power of using SQL and big data tools like Google BigQuery to gain insights into large datasets.
