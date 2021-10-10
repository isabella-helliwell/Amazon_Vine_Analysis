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



# Analysis
<b>PySpark</b> is used to preform the ETL process to extract the dataset, transform the data, and connect to an </b>AWS RDS instance</b>, and finally to load
the transformed data into <b>pgAdmin</b>.
The second part of the analysis is to determine if there is any bias toward favorable reviews from Vine members in the dataset

# Coding
For this challenge, the data tables in SQL is to created by the code provided challenge_schema.sql.
See the <b><ins>Amazon_Reviews_ETL.ipyng </ins></b> and <b><ins>Vine_Review_Analysis.ipynb</b><ins>. 
