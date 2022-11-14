# Fetch_Reward-Data_Analyst
This project is a part of the takehome assessment for the role of Data Analyst at **Fetch Rewards** (https://www.fetchrewards.com/).

### Project Status: [Complete]

## Table of contents
* [Project Introduction-Objective](#project-introduction-objective)
* [Requirements](#requirements)
* [Methods Used](#methods-used)
* [Technologies](#technologies)
* [Project Description](#project-description)
    + [Data Sources](#data-sources)
    + [Approach](#approach)
* [Files consisting names and path](#files-consisting-names-and-path) 
* [Contact](#contact)


## Project Introduction-Objective
[(Back to table of contents)](#table-of-contents)

My task is to reason about data and how you communicate your understanding of a specific data set to others.

An understanding of the data schema and analysing the dataset is the biggest task of a Data Analyst and this challenge is all about that. 

## Requirements
[(Back to table of contents)](#table-of-contents)

* Review unstructured JSON data and diagram a new structured relational data model
* Generate a query that answers a predetermined business question
* Generate a query to capture data quality issues against the new structured relational data model
* Write a short email or Slack message to the business stakeholder

## Methods Used
[(Back to table of contents)](#table-of-contents)

* Data Preparation/Cleaning
* Schema Designing (ER- Diagram)
* Data Visualization
* Data Querying

## Technologies
[(Back to table of contents)](#table-of-contents)

* Python
* SQL
* Pandas, jupyter

## Project Description
[(Back to table of contents)](#table-of-contents)

### Data Sources

We are using three data files namely receipts, users, brand data given to us in the challenge. The data files can be found in Data Folder and metadata about the columns in each of the files are also in Data Folder under metadata file.

### Approach

### i) Understanding the data

To understand the data and the features than can be most useful, I first read the problem statement and learned about the data files and the columns present in it. This helped me understand the problem in more depth and what can help me in building the ER Diagram.

### ii) Cleaning the data

I first looked at the data files individually and found that there were few issues with the data to begin with. Firstly, there were some columns in all the data files which consisted of the values in the dictionary format, so I normalized them. After this I found there were many null values, although I did not impute the values now, but in future this would be the first step to work onto. I also removed the duplicated rows in the Users table which were almost half of the rows, as this is a major data quality issue and we should check the consistency before anything else, thus first step would be to check for these entries and how they are getting duplicated.

Finally after cleaning the data and making it in the form to perform operations on I saved all three files in the csv format as final files under the data folder in this repository.

### iii) Entity Relation Diagram

When diving deep into the data columns that were provided to us, one major issue that I found was there was no clear way to connect brands with users and the receipts and there were many null values, anyways null values is the attribute of real world data, but to make a better schema with which we can maintain ACID properties, I created two new tables : Transaction and Items.

Transaction table consists of item_id, user_id, receipt_id which can be used to connect with Items table, Users table and Receipts table. Then we needed to have some table which can help us connect with the brands table, thus items table: this table has all the information about the item that is being sold, listed or bought. It also has brand_id and this is the table which helps in connecting the Receipts, Users with Brands table. With this schema design we can analyse the data easily. This can help in finding the answers to the questions like which brands are more popular these days or which brands were popular a year before. This helps in finding the trend and doing some analysis for the business to grow.

### iv) SQL Queries

After creation of the Entity Relation Diagram, it was fairly simple to write the queries and output the sequence we need to know. For the SQL query, I used pandas SQL, but the structure of the query is same as PostgreSQL and MySQL.


## Files consisting names and path

### Data Files Folder 
This folder consists 4 files. 
1. Dengue Features Train - Training dataset for the challenge
2. Dengue Features Test - Test dataset
3. Training Label - Target class which is total cases is given by city and time.
4. Submission File - Week of the year and City for which we have to predict the total cases.
