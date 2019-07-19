
# Project: Data Modeling with Postgres

## Introduction
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

## Project Description
In this project, I will apply what I've learned on data modeling with Postgres and build an ETL pipeline using Python. To complete the project, I will need to define fact and dimension tables for a star schema for a particular analytic focus, and write an ETL pipeline that transfers data from files in two local directories into these tables in Postgres using Python and SQL.  

## Database Schema
For this project, I have used a start schema to create the database sparkifydb. A star schema was chosen for this project due to its flexibility  for the analytics team to query sparkifydb. The database is composed of a fact table and four dimensional tables. Below are the descriptions of the tables contained in sparkifydb

**songplays** (Fact) : songplays is the fact table at the center of the star schema. This table includes information on 

**users** (Dimensional):
The users table is a dimensional table which contains information on of the streaming services users

**songs** (Dimensional):
The songs table is a dimensional table which contains information on the songs available for streaming

**artists** (Dimensional):
The artists table is a dimensional table which contains information on all of the artists available for streaming

**time** (Dimensional):
The time table is a dimensional table that keeps track of the times music was streamed from a streaming service. 

## Files included

- **sql_queries.py**: This file includes the queries used for dropping existing tables, creating new tables, and inserting data into sparkifydb.
- **create_tables.py**: This file initializes sparkifydb and executes the queries from sql_queries.py to create the tables.
- **etl.py**: This file is used to extract, transform, and load data from the songs and logs datasets within the data folder. First, the songs dataset is processed, then the log data is processed. Once the dataset is processed from both of the sets, it is loaded into sparkifydb using the insert queries from sql_queries.py

## Running this project
To run this project, you must first run create_tables.py to create sparkifydb and its associated tables. After you run create_tables.py, run etl.py to extract, transform, and load the data into the database. Once both the files have been run, you can use test.ipynb to see if the values were correctly inserted into the database.
