# UK Online Retail: Sales Analysis, Customer Segmentation and SAP-Aligned Data Model

A Python analysis of real transaction data from a UK-based online giftware retailer, covering data cleaning, sales and cancellation analysis, RFM customer segmentation and a mapping of the cleaned data to an SAP SD billing structure. All monetary values are in pounds sterling (£).

> Personal portfolio project using a public dataset. No live SAP system was used.

## Dataset
- **Source:** UCI Machine Learning Repository, *Online Retail II* (transactions from 01/12/2009 to 09/12/2011)
- **Content:** invoices, stock codes, descriptions, quantities, dates, unit prices (£), customer IDs and countries

## Business Questions
1. How does monthly revenue change over time, and is there seasonality?
2. Which products and countries generate the most revenue?
3. How much revenue is lost to cancelled orders?
4. How can customers be segmented by purchasing behaviour, and how concentrated is revenue?
5. How would this data look in an SAP SD billing structure?

## Method
1. **Audit:** missing values, duplicates, negative quantities and prices
2. **Cleaning:** removed duplicates, non-product codes and invalid rows; separated cancellations
3. **Analysis:** monthly trend, top products and markets, cancellation rate and value
4. **RFM segmentation:** Recency, Frequency and Monetary scores (quintiles) grouped into five segments
5. **SAP-aligned model:** VBRK, VBRP, KNA1 and MAKT tables following SAP SD naming, with a reconciliation check

## Key Findings
- Data: 1,067,371 raw transaction lines; 1,003,607 valid sales lines after cleaning (01 Dec 2009 to 09 Dec 2011).
- Total net revenue was £19,657,288 across 39,523 invoices.
- Revenue peaked in November 2011 (£1,453,266); the lowest complete month was February 2011 (£508,015).
- Revenue for December 2010 to November 2011 was +2.5% compared with December 2009 to November 2010 (complete months only).
- The top 10 products generated 7.8% of revenue.
- The UK accounted for 85.5% of revenue; the largest export market was EIRE (£633,269).
- 15.8% of invoices were cancellations, worth £716,716 (3.6% of net revenue).
- 13.1% of revenue came from transactions without a Customer ID and was excluded from segmentation.
- Across 5,853 identified customers, the Champions segment made up 22.0% of customers and 72.0% of revenue.
- 966 customers were classed as At Risk, representing £369,804 of historical revenue.
- The top 20% of identified customers generated 77.2% of identified revenue.

## Charts

![Monthly revenue](images/01_monthly_revenue.png)

![Top products](images/02_top_products.png)

![Top export markets](images/03_top_export_markets.png)

![RFM segments](images/04_rfm_segments.png)

## Recommendations
1. Run a win-back campaign for At Risk customers.
2. Introduce a loyalty programme for Champions and Loyal customers.
3. Investigate the products and invoices with the highest cancellation value.
4. Capture customer IDs at checkout to improve segmentation.
5. Plan stock and staffing around the seasonal peak.

## Limitations
- One retailer, December 2009 to December 2011; may not reflect current behaviour.
- The final month is incomplete and excluded from trend calculations.
- Transactions without a Customer ID are excluded from RFM analysis.
- RFM thresholds follow a standard convention and are not optimised.
- Cancellations are not linked to original invoices.
- SAP tables are a structural mapping of public data, not an extract from SAP.

## Tools
Python 3, pandas, NumPy, matplotlib, Google Colab

## Contact

[LinkedIn](https://www.linkedin.com/in/shirin-aghaei/)
