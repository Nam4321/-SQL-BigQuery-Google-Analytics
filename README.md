# I. Introduction
This project contains an eCommerce dataset that I will explore using SQL on Google BigQuery. The dataset is based on the Google Analytics public dataset and contains data from an eCommerce website.

# II. Exploring the Dataset
In this project, I will write 08 query in Bigquery base on Google Analytics dataset

# Query 01: calculate total visit, pageview, transaction for Jan, Feb and March 2017 (order by month)
### SQL code
![Code Q1](https://github.com/Nam4321/-SQL-BigQuery-Google-Analytics/assets/80372192/d9f5ee2a-9bd6-4bb5-9320-c44d566a24fd)
### Query results
![KB Q1](https://github.com/Nam4321/-SQL-BigQuery-Google-Analytics/assets/80372192/d2149666-cafb-4bc3-b4ea-5b93da93e927)
# Query 02: Bounce rate per traffic source in July 2017 (Bounce_rate = num_bounce/total_visit) (order by total_visit DESC)
### SQL code
![Code Q2](https://github.com/Nam4321/-SQL-BigQuery-Google-Analytics/assets/80372192/63676e8f-d599-4b66-a26c-bdcf0b95c8f9)
### Query results
![KQ Q2](https://github.com/Nam4321/-SQL-BigQuery-Google-Analytics/assets/80372192/df61234c-1d19-45f9-ab6b-ac22c4c4e184)
# Query 3: Revenue by traffic source by week, by month in June 2017
### SQL code
![Code Q3](https://github.com/Nam4321/-SQL-BigQuery-Google-Analytics/assets/80372192/7e53201b-bf9e-4292-890f-7c32104fdc68)
### Query results
![KQ Q3](https://github.com/Nam4321/-SQL-BigQuery-Google-Analytics/assets/80372192/cfc3d319-194b-4940-bdd0-be2b330b9456)
# Query 04: Average number of pageviews by purchaser type (purchasers vs non-purchasers) in June, July 2017.
### SQL code
![Code Q4](https://github.com/Nam4321/-SQL-BigQuery-Google-Analytics/assets/80372192/3fde572e-41a2-434c-8368-a7a8ff17c041)
### Query results
![KQ Q4](https://github.com/Nam4321/-SQL-BigQuery-Google-Analytics/assets/80372192/19af1385-7544-420a-aa98-77a32821a5d8)
# Query 05: Average number of transactions per user that made a purchase in July 2017
### SQL code
![Code Q5](https://github.com/Nam4321/-SQL-BigQuery-Google-Analytics/assets/80372192/d1f639bb-fcc4-41c0-a3fd-1716243b6cb4)
### Query results
![KQ Q5](https://github.com/Nam4321/-SQL-BigQuery-Google-Analytics/assets/80372192/75eaa8b1-8121-4868-865c-162c31fc9a65)
# Query 06: Average amount of money spent per session. Only include purchaser data in July 2017
### SQL code
![Code Q6](https://github.com/Nam4321/-SQL-BigQuery-Google-Analytics/assets/80372192/c21b3c6e-4b63-4f2a-97d3-a0841424c9f8)
### Query results
![KQ Q6](https://github.com/Nam4321/-SQL-BigQuery-Google-Analytics/assets/80372192/c8a9f549-e93c-4f0f-a908-9c3e82152160)
# Query 07: Other products purchased by customers who purchased product "YouTube Men's Vintage Henley" in July 2017. Output should show product name and the quantity was ordered.
### SQL code
![Code Q7](https://github.com/Nam4321/-SQL-BigQuery-Google-Analytics/assets/80372192/c496e623-fb8f-4b6d-b088-b08f5325fd75)
### Query results
![KQ Q7](https://github.com/Nam4321/-SQL-BigQuery-Google-Analytics/assets/80372192/bec41556-3162-44ad-bf24-d53fa2149e3e)
# Query 08: Calculate cohort map from product view to addtocart to purchase in Jan, Feb and March 2017. For example, 100% product view then 40% add_to_cart and 10% purchase.
# Add_to_cart_rate = number product  add to cart/number product view. Purchase_rate = number product purchase/number product view. The output should be calculated in product level.
### SQL code
![CODE Q8](https://github.com/Nam4321/-SQL-BigQuery-Google-Analytics/assets/80372192/63aabd3c-d7ba-4246-befa-8b9328548369)
### Query results
![KQ Q8](https://github.com/Nam4321/-SQL-BigQuery-Google-Analytics/assets/80372192/7d8a0004-d76f-44f0-94b3-61e3c7d68f78)

# III. Conclusion

In conclusion, my exploration of the eCommerce dataset using SQL on Google BigQuery based on the Google Analytics dataset has revealed several interesting insights.
By exploring eCommerce dataset, I have gained valuable information about total visits, pageview, transactions, bounce rate, and revenue per traffic source,.... which could inform future business decisions.
To deep dive into the insights and key trends, the next step will visualize the data with some software like Power BI,Tableau,...
Overall, this project has demonstrated the power of using SQL and big data tools like Google BigQuery to gain insights into large datasets.
