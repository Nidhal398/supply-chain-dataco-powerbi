# KPI dictionary

The formulas below are transcribed from the model's DAX measures. Currency units and the exact source-column semantics follow the supplied dataset/model; KPI values in the README are dashboard-displayed values and were not recalculated independently.

| KPI | Definition in the model | Notes |
|---|---|---|
| Net Sales | `SUM(Fact_OrderItems[Order Item Total])` | Sum of order-item totals. |
| Total Profit | `SUM(Fact_OrderItems[Benefit per order])` | Sum of benefit per order item. |
| Profit Margin % | `[Total Profit] / [Net Sales]` | Ratio of total profit to net sales. |
| Discount % | `SUM(Fact_OrderItems[Order Item Discount]) / SUM(Fact_OrderItems[Gross Sales])` | Discount ratio over gross sales; this is not an average of row-level discount percentages. |
| Total Orders | `DISTINCTCOUNT(Fact_OrderItems[OrderId])` | Distinct order IDs. |
| Total Customers | `DISTINCTCOUNT(Fact_OrderItems[CustomerKey])` | Distinct customer keys. |
| Late Items | Count of fact rows where `Late_delivery_risk = 1` | Item-level count. |
| Shipped Items | Total items excluding rows with order status `Shipping canceled` | Denominator used by late delivery rate. |
| Late Delivery Rate | `[Late Items] / [Shipped Items]` | Measure is based on items, not distinct orders. |
| Repeat Customer % | Customers with more than one distinct `OrderId` divided by customers in the current filter context | Filter context affects both numerator and denominator. |
| Countries Served | Distinct country count | Uses the model's geography fields. |
| Countries at Loss | Count of countries where `[Total Profit] < 0` | Evaluated within current filter context. |

## Dashboard-displayed values

The project brief reports these values as visible in the dashboard: Net Sales **$33M**, Total Profit **$4M**, Profit Margin **12.0%**, approximately **66K orders**, approximately **21K customers**, **164 countries**, Late Delivery Rate **57.3%**, **10 countries at loss**, and discount ratio **10.1%**. These are presented as report values, not as independently validated results.

The project brief also reports First Class at 100% late, broadly similar late rates across markets, roughly stable margin around 12% across discount bands, and the United States as the top country. Those observations depend on the report's filter context and visual definitions.
