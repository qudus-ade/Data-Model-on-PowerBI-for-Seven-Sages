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
* **Date**:
  * Date table was created using the `Date.StartOfYear()` for the start date and `Date.EndOfYear()` for the end date.
  * SSBC's Fiscal year begins on October 1st and runs until September 30th. This was factored in to the analysis.
  * The _Date_ table was marked as the Date Table in Power BI.

## Relationships
_Sales_ table is the Fact Table while _Products, Customer, USD-CAD Exchange Rates,_ and _Date_ are the Dimension Tables.
_Many to 1_ relationships are used to connect the _Sales_ table to the dimension tables.

![image](https://user-images.githubusercontent.com/67699946/182036142-bbc51a26-4d51-4a01-9f83-e2eb7b637ab7.png)

## Measures Calculated
The following measures were calculated for analysis:
* Sales (USD)
* Cost of Sales (USD)
* Gross Profit Margin (%)
* Sales (CAD)
* % Unit Sales by Product
* % Gross Profit by Product

