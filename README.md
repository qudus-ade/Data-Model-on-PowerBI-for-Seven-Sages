# Data-Model-on-PowerBI-for-Seven-Sages
A data model and Power BI report for Seven Sages Brewing Company that combines information from all over the company

## Introduction
This project is the first of three projects in the Udacity Data Analysis and Visualization with Microsoft Power BI Nanodegree Program. A data model was created for Seven Sages Brewing Company (SSBC) to enable the company's CFO quickly review and analyze what beers sell well and which ones generate the highest profitability.

## Data
The data listed below were loaded into Power BI using _Get Data_ in Power Query
* SSBC Product Offerings (PDF): A list of the product offerings offered by SSBC
* Sales Log Folder: A folder containing Excel files of monthly sales
* CFO Metrics Tracker (Excel file)
* USD-CAD Exchange Rates (.csv)
* Customer List (.txt)

## Data Preparation
Several transformation processes were carried out in Power Query. Some of them are listed below
* **Product offerings**:
  * Unwanted column (Description) was removed
  * Blank rows were removed
  * The table was merged with CFO Metrics Tracker table on Product ID
* **Customer**
  * Clean data correcting misspelled _Canada_ spelt as _Canarda_
  * A _Currency_ column was created using the _Country_ column. The column contains CAD for customers in Canada and USD for United States.
