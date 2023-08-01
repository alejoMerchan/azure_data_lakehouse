Building an Azure Data Lake for Bike Share Data Analytics
==============================================================

# Context

This is the solution of the assignment "Building an Azure Data Lake for Bike Share Data Analytics" from
UDACITY course "Data Engineering with Microsoft Azure".

# Problem

## Project Overview

Divvy is a bike sharing program in Chicago, Illinois USA that allows riders to purchase a pass at a kiosk or
use a mobile application to unlock a bike at stations around the city and use the bike for a specified amount
of time.
The bikes can be returned to the same station or to another station.
The City of Chicago makes the anonymized bike trip data publicly available for projects like this where we can
analyze the data.

Since the data from Divvy are anonymous, we have created fake rider and account profiles along with fake payment
data to go along with the data from Divvy. The dataset looks like this:


![initial model](/model.png)

The goal of this project is to develop a data warehouse solution using Azure Synapse Analytics. You will:

Design a star schema based on the business outcomes listed below;
Import the data into Azure Databricks using Delta Lake to create a Bronze data store;
Create a gold data store in Delta Lake tables;
Transform the data into the star schema for a Gold data store;

# Solution

## Star Schema

![star schema](/star_schema.png)

## Extract
- Python code to extract information from CSV files stored in Databricks and write it to the Delta file system.
- Python code that picks files up from the Databricks file system storage and writes it out to Delta file locations.

Pyspark code to extract the data from the csv's a put it in the delta is in the script: /extract_data

## Load
- Python code that creates tables and loads data from Delta files. The learner should use spark.sql statements to create the
tables and then load data from the files that were extracted in the Extract step

Pyspark code to load the data from the delta location to the staging_tables is in the script: /load

## Transform
- The fact table Python scripts should contain appropriate keys from the dimensions. In addition, the fact table 
scripts should appropriately generate the correct facts based on the diagrams provided in the first step.
- The transform scripts should at minimum adhere to the following: should write to delta; should use overwrite mode;
save as a table in delta.

Pyspark code to create the dimensions and fact tables is in the script: /transform






