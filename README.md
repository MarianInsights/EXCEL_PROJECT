# 📊 2025 Sales Dashboard

An Excel dashboard tracking a full year of sales, expenses, and profit, broken down by day, month, and quarter, with recommendations based on the underlying trends. Built entirely in Excel, from raw data through a calendar based date model to a finished dashboard.

![Dashboard Overview](Sales%20Dashboard%20for%202025%20(Excel).png)
*Sales dashboard for 2025, with KPI summary and recommendations*

## 📌 Overview

The dashboard works through a year of daily sales and expense data to answer a few practical business questions:

* What do total sales, expenses, and profit look like for the year?
* Which day of the week and which month perform best?
* How is sales performance trending across the four quarters?
* Where should attention go next, based on what the data shows?

## 📊 Data Source

The dataset is synthetic, created for practice rather than sourced from an actual business. It contains 257 weekday records (Monday through Friday) spanning January 2 to December 30, 2025, with daily sales and expense figures. It was designed to resemble a realistic small business sales log, structured to support date based analysis and aggregation.

## 🧹 Data Cleaning and Modeling

The Raw_Data sheet contains a date, a sales figure, and an expense figure for each day. The cleaned data, calendar lookups, and summary tables were built in Power Query:

* Added Profit and Profit_Margin as custom columns, calculated from sales and expenses for each day.
* Built a separate Calendar query as a date lookup table, then merged it into the main query to pull in Day_Name, Month_Name, Quarter, and Week of Year for every date, rather than hardcoding those values.
* Added an Index column to support ordering and referencing rows across the other sheets.
* Used Power Query's grouping to aggregate the cleaned data into the Monthly_Summary and Weekday_Analysis tables, rolling up sales, expenses, and profit by month and weekday.

This mirrors a date dimension table, the structure used in BI tools like Power BI, recreated using Power Query merges in Excel. It allows the daily data to be grouped and summarized by weekday, month, and quarter without repeating that logic across sheets.

## 🛠️ Process

1. Raw_Data: the starting point, daily date, sales, and expenses.
2. Clean Data: built in Power Query, with profit and profit margin calculated, then weekday, month, quarter, and week merged in from the Calendar query.
3. Monthly_Summary and Weekday_Analysis: also built in Power Query, grouping the cleaned data to aggregate sales, expenses, and profit by month and weekday.
4. DashBoard: the final dashboard, pulling KPIs and charts from the summary sheets and pairing them with written recommendations.

## 📈 Dashboard Breakdown

**KPI Summary**

| Total Sales | Total Expenses | Total Profit | Best Day | Best Month |
|---|---|---|---|---|
| 3.8M | 260.1K | 3.6M | Friday | November |

**Visuals included:**

| Chart | Type | What it shows |
|---|---|---|
| Distribution by Month | Line | Sales by month across the year, generally trending upward toward the later months |
| Distribution by Day | Bar | Sales by weekday, with Friday and Monday well ahead of the rest and Thursday the lowest |
| Sales Distribution by Quarter | Pie | Sales by quarter, increasing steadily from Q1 through Q4 |

## 💡 Recommendations

Based on the dashboard findings:

* Targeted campaigns should be introduced in the first quarter, since Q1 brings in noticeably less sales than the rest of the year.
* Expense control is currently effective, so the focus going forward should be on monitoring the expense to sales ratio monthly rather than cutting further.
* Staffing should be aligned with demand: maximize capacity on Fridays and Mondays, and streamline resources on Thursdays, the consistently slowest day.

## 🧰 Tools Used

* Microsoft Excel, using:
  * Power Query, to build the calendar lookup table, merge it into the main data, calculate profit and profit margin as custom columns, and group the data into the monthly and weekday summary tables
  * Pivot tables and charts, to build the dashboard

## 📁 Repository Contents

* Sales_Dashboard.xlsx: full workbook with raw data, cleaned data, summary sheets, calendar table, and final dashboard
* images/: dashboard screenshots

## 🔍 How to View

Download Sales_Dashboard.xlsx and open it in Excel. The workbook contains six sheets:
1. DashBoard: final dashboard with KPIs, charts, and recommendations
2. Raw_Data: original daily sales and expense data
3. Clean Data: cleaned data with profit, profit margin, and calendar based fields added
4. Monthly_Summary: sales, expenses, and profit aggregated by month
5. Weekday_Analysis: sales, expenses, and profit aggregated by weekday
6. Calendar: date lookup table used to derive weekday, month, and quarter fields
