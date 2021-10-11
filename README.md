# Amazon_Vine_Analysis
# Project Overview
The aim of this project is to analyze Amazon reviews written by members of the paid Amazon vine program. For this we have access
to Amazon datasets, each containing reviews of a specific product. The dataset chosen for this analysis is the videogame reviews dataset.
https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Video_Games_v1_00.tsv.gz .

# Resources
* Google hosted notebook: Google Colaboratory
* Analytics engine: Spark, pySpark
* Amazon Web Services AWS
* pgAdmin4 PostgreSQL

# Coding
For this challenge, the data tables in SQL is created by the codes provided in <b><ins>challenge_schema.sql</b></ins>.
See the <b><ins>Amazon_Reviews_ETL.ipyng </ins></b> and <b><ins>Vine_Review_Analysis.ipynb</b><ins>.

  
  
# Analysis
## Deliverable 1.
<b>PySpark</b> is used to preform the ETL process to extract the dataset, transform the data, and connect to an </b>AWS RDS instance</b>, and finally to load
the transformed data into <b>pgAdmin</b> data tables.
Below shown are four screen grabs from some of the data input in the tables

Output customer_table pgAdmin

![customer_table](https://user-images.githubusercontent.com/85843030/136719444-4f4f98ea-8279-4e9e-ba86-15f3e4e91047.png)



Output products_table pgAdmin

![products_table](https://user-images.githubusercontent.com/85843030/136719488-26339ac1-e636-45b2-9392-d8f36bf4532b.png)



Output review_id_table pgAdmin

![review_id_table](https://user-images.githubusercontent.com/85843030/136719512-06e16787-0654-455a-a8a0-0a275ede2a84.png)



Output vine_table pgAdmin

![vine_table](https://user-images.githubusercontent.com/85843030/136719558-62ce594f-b4e5-4ed3-b074-019b28bf13c6.png)



## Deliverable 2.
The second part of the analysis is to determine if there is any bias toward favorable reviews from Vine members in the dataset. This is done by using
pySpark:
1. The dataset is filtered for a total votes count that is >=20
2. The above data is filtered again to create a new DataFrame to retrieve all the rows where helpful_votes/total_votes =>50%
3. New DataFrame is created for the data filtered for the paid Vine reviews and the unpaid vine reviews
4. Finally the total number of reviews, the number of 5-star reviews, and the percentage of 5-star reviews for the paid and unpaid reviews is calculated.

# Results
* Vine Reviews (paid) and non-Vine reviews (unpaid):
As shown below, there is 94 reviews from Vine paid customers and 40471 reviews from the Vine unpaid customers.

![image](https://user-images.githubusercontent.com/85843030/136699539-d74a2f8f-830b-4be8-9eed-1590c828bdec.png)


* 5-star reviews for Vine Reviews (paid) and non-Vine reviews (unpaid):
As shown in the screen grab, there are 48 five star paid Vine reviews and 15663 unpaid five star Vine reviews.

![image](https://user-images.githubusercontent.com/85843030/136699812-553e2ca3-af38-4615-aa6d-aca9d55d0d15.png)


* Percentage 5-star reviews for Vine Reviews (paid) and non-Vine reviews (unpaid);
Below shown are the two percentage values for paid and unpaid Vine reviews.

![image](https://user-images.githubusercontent.com/85843030/136700146-1a917755-0acb-460e-94be-ba2d50361e9d.png)

# Summary
Looking at the results one could draw the conclusion that the Vine reviews are more biast. However, in order to truly support this, one would have to 
analyse each review to see if this trend is recognised for the other review datasets.

We can also look at the mean value across the star ratings to see if the average star rating is higher for the paid vine reviews than for
the unpaid vine reviews.
From tables we can see that the average star rating for the paid reviews is approximately <b>25.5% higher</b> than for the average unpaid review.(4.202/3.348)

![image](https://user-images.githubusercontent.com/85843030/136704517-23ca36f6-90d1-4e1a-b2ab-2893127a98b6.png)

<b><ins>Conclusion:</b></ins> Based on the above analysis, the conclusion is made that the Vine-paid reviews are biast. However, in order to support this hypothesis, all data sets need to be analysed.
