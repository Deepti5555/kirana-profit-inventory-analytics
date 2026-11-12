# kirana-profit-inventory-analytics
Profit and inventory analysis of a kirana store using Python and Power BI
# Kirana Store: Profit and Inventory Analytics

An end-to-end data analytics project that finds where a small kirana store has money stuck in stock, which products it should reorder, and which ones it should stop buying.

**Tools:** Python (pandas, numpy, matplotlib), Power BI, VS Code, Git

## Problem

A small shopkeeper often has too much stock of some items and runs out of others. This project answers three questions:

1. Which products and categories earn the most profit?
2. How much money is stuck in overstock and slow-moving stock?
3. What should the shop reorder, stop ordering, or clear with a discount?

## Dataset

- Real product names and MRP from the BigBasket product dataset (Kaggle): 157 Excel files, 57,013 rows
- Cost price, demand, stock and lead time are **simulated**, because the dataset has only prices. The simulation is documented in the notebook and the numbers are meant to demonstrate the method, not to describe a real shop.

## Approach

1. **Combine:** 157 Excel files merged into one table
2. **Clean:** removed duplicates and rows with missing or zero MRP (57,013 to 42,555 rows)
3. **Build the store:** 600 kirana-style products chosen with category quotas
4. **Simulate:** cost price, daily demand, stock, lead time and reorder level
5. **Analyse:** category profit, days of cover, stock status, ABC analysis
6. **Decide:** three action lists (reorder, stop ordering, clearance)
7. **Visualise:** 2-page Power BI dashboard

## Key findings

| Finding | Value |
|---|---|
| Revenue (90 days) | about Rs 1.04 crore |
| Profit (90 days) | about Rs 19.5 lakh (18.8% margin) |
| Inventory value | about Rs 55.3 lakh |
| Stock in overstock + dead/slow stock | about 45% of inventory value |
| Excess stock beyond 45 days | about Rs 20.9 lakh |
| Class A products | about 64% of inventory value |
| Class A products in overstock | 39 products, about Rs 13.9 lakh |
| Class A products that need reordering | 8 products |

Class A products earn most of the profit, yet they hold both the biggest overstock and some stockouts. This suggests ordering is not matched to demand.

## Action lists (Power BI page 2)

- **Reorder now:** 40 products below their reorder level
- **Stop ordering:** 39 class A products with more than 90 days of stock
- **Clearance:** 44 class C products that are slow-moving

## Files

| File | What it is |
|---|---|
| `analysis.ipynb` | Full Python analysis |
| `kirana_final.csv` | Final 600-product table |
| `kirana_action_plan.xlsx` | Reorder, stop-ordering and clearance lists |
| `kirana_dashboard.pbix` | Power BI dashboard (open with Power BI Desktop) |

## Limitations

Cost price, demand and stock are simulated, so the findings show how the framework works. With a real shop's sales and stock data, the same notebook and dashboard would give real answers.

## Author

Deepti Garkoti
