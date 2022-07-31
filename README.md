# Data-Model-on-PowerBI-for-Seven-Sages
A data model and Power BI report for Seven Sages Brewing Company that combines information from all over the company

## Introduction
This project is the first of three projects in the Udacity Data Analysis and Visualization with Microsoft Power BI Nanodegree Program. A data model was created for Seven Sages Brewing Company (SSBC) to enable the company's CFO quickly review and analyze what beers sell well and which ones generate the highest profitability.

Check [here](https://github.com/qudus-ade/Data-Model-on-PowerBI-for-Seven-Sages/blob/main/SSBC%20Data%20Model%20and%20Report.pbix) for the Power BI report.

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

## Data Modelling
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
* Servings Sold

## Analysis and Report
**1. Sales and Gross Profit Margin by Customer and Customer Type**

![image](https://user-images.githubusercontent.com/67699946/182036748-552dfa9d-1a57-4185-bd5f-895e783ea0ce.png)

**Executive Summary**: While the highest sales by customer type is Bar with $68,797, the highest gross profit margins are SSBC Tasting Room with 60.8%. Among individual customers, the highest sales are Barrel's Best with a total of $52,676 while the highest gross profit margins (other than those in tasting room) are The Black Bear with 37.9%.

**2. Percentage of Gross Profit and Unit Sales by Product**

![image](https://user-images.githubusercontent.com/67699946/182036769-7509a5ab-67b9-4f79-94a6-473210695957.png)

**Executive Summary**: Bamboo Grove Maibock has the highest sales and gross profit share. Despite having 16.1% share of sales, Scholar Saison has only 0.3% gross profit share while in contrast, Han Dynasty Spied Lager has only 4.1% sales share and collects a 10.5% gross profit share.

**3. Most Profitable Product per Serving**

![image](https://user-images.githubusercontent.com/67699946/182036904-88291a7d-f8e8-4b0e-ac17-6e968a689e90.png)

**Executive Summary**: Keg is the most profitable with $44.62 Gross Profit per serving while Six-Pack is the least profitable with $2.22 Gross Profit per serving. The company made a loss of $0.14 for Six-Pack's Scholar Saison.

**4. Seasonality**

![image](https://user-images.githubusercontent.com/67699946/182036998-1160c227-cad6-453c-b638-d9a23bfc8dc4.png)

**Executive Summary**: Imperial Poet Porter has its least sales between May and June then it continues to increase from September to January. Scholar's Saison remain consistent for most months but started increase by April and sees a spike in June. Henan Hops Wheat Bear experienced its highest sales in October. Bamboo Grove Maibock is consistent but sees a spike in May and November.

You can check the Power BI report [here](https://github.com/qudus-ade/Data-Model-on-PowerBI-for-Seven-Sages/blob/main/SSBC%20Data%20Model%20and%20Report.pbix)
