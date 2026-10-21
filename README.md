# Demand Forecasting and Inventory Optimization

A complete demand-to-inventory workflow on real retail data: weekly demand forecasting, ABC analysis, EOQ, safety stock and reorder points.

**Dataset:** Online Retail II (UK online giftware retailer, Dec 2009 to Nov 2011), cleaned from 1,067,371 to 1,008,690 valid rows.
**Tools:** Google Sheets (forecasting, ABC analysis, EOQ, safety stock and reorder point).

## Business question
How much will each top product sell next week, and how much should the shop order, and when?

## What was done
1. **Data cleaning:** removed duplicates, cancellations, invalid quantities and prices, non-product codes, and orders cancelled in full. Kept complete weeks only.
2. **Forecasting:** 3-week moving average vs exponential smoothing (alpha 0.1, 0.3, 0.5) for the 10 highest-value products. Accuracy measured by MAD on the last 12 weeks.
3. **ABC analysis:** 4,870 products ranked by annual sales value (A up to 80%, B up to 95%, C the rest).
4. **EOQ:** order quantity that minimises ordering plus holding cost.
5. **Safety stock and reorder point:** for a 95% service level and a 2-week lead time.

## Key results
- **1,052 of 4,870 products (22%) make 80% of sales value.**
- Exponential smoothing (alpha 0.1) was best for 7 of 10 products; the 3-week moving average for Party Bunting and Small Popcorn Holder; alpha 0.5 for the seasonal Paper Chain Kit.
- Forecast error (MAD) is about 26% to 57% of average weekly sales, which reflects lumpy wholesale demand.
- EOQ ranges from about 711 to 5,096 units, or 8 to 18 orders per year.
- Safety stock ranges from 410 to 2,107 units; reorder points from 741 to 3,707 units.

## Assumptions
Order cost 50 GBP per order; holding cost 20% of unit price per year; lead time 2 weeks; service level 95% (z = 1.65). These are not in the dataset.

## Limitations
Assumed costs and lead time; demand is gross sales (partial returns not netted); prices are selling prices, not costs; forecasts tested on only 12 weeks; lumpy and seasonal items have large errors; inventory calculations cover the top 10 products only.

## Files
- `PROJECT_2_DEMAND_FORECASTING_INVENTORY.xlsx`: full workbook (one tab per product, ABC analysis, summary)
- `Project2_Report_Demand_Forecasting_Inventory.docx`: full report
- `OR2_weekly_demand_top10.csv` and `OR2_product_table_for_ABC.csv`: cleaned input data
- `Forecast_results_all_10_products.csv`: forecast comparison

## Author
Ukkusuri Bharath (Roll No. 124107009), Production and Industrial Engineering, National Institute of Technology Kurukshetra. Open to feedback.
