# Olist E-Commerce Performance Dashboard (Power BI)

An interactive Power BI dashboard analysing ~99K orders (2016–2018) from the
Brazilian marketplace Olist: sales, seller concentration, delivery performance
and customer reviews.

**Data:** [Brazilian E-Commerce Public Dataset by Olist (Kaggle)](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
**Tools:** Power BI, Power Query, DAX

![Sales page](./Sales%20Page.png)
![Delivery page](./Delivery%20Page.png)

## Business questions
1. How do revenue and orders trend over time?
2. Which categories drive the most revenue and orders?
3. What is the delivery time, and what share of orders arrive late?
4. Which states have the highest late-delivery rates?
6. How does freight % of price by state?
7. Do late deliveries lead to lower review scores?
8. What share of customers are repeat buyers?

## Key findings
- R$13.59M revenue from ~98.7K orders; average order value R$137.75.
- The top 10% of sellers generate **68%** of revenue.
- Only **3.12%** of customers placed more than one order.
- **8.11%** of delivered orders arrived late; average delivery took ~12 days.
- Late rates are highest in AL (24.0%), MA (19.5%) and PI (15.9%).
- Late orders average roughly 2.5 stars versus roughly 4.3 for on-time orders.

## Approach
- **Power Query:** typed columns, kept the latest review per order, merged English
  category names, aggregated geolocation to one row per zip, built delivery-time
  and late-delivery fields.
- **Data model:** relational model with `orders` as the hub, one-to-many
  single-direction relationships, and a custom Date table.
- **DAX:** revenue, AOV, late %, repeat-customer %, top-10% seller share, and
  measures using `CROSSFILTER` to analyse reviews and late % by category.

