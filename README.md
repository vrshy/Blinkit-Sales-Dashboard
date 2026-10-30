# BlinkIT Grocery Sales Dashboard (Power BI)

An interactive Power BI dashboard that analyzes sales, customer ratings and outlet performance for BlinkIT grocery data, built to answer: **which products, outlet types and locations drive the most sales?**

![Dashboard](dashboard_screenshot.png)

## Business Requirement
Conduct a comprehensive analysis of Blinkit's sales performance, customer satisfaction and inventory distribution to find key insights and optimization opportunities, using KPIs and visualizations in Power BI.

**KPIs required:** Total Sales, Average Sales, Number of Items, Average Rating

**Analysis requirements (all covered in the dashboard):**
1. Total sales by **fat content**, with average sales, item count and rating
2. Total sales by **item type**
3. **Fat content by outlet** for total sales
4. Total sales by **outlet establishment** year
5. Percentage of sales by **outlet size**
6. Sales by **outlet location**
7. All metrics by **outlet type**

## Dataset
- **Source:** BlinkIT grocery sales data (`BlinkIT_Grocery_Data.xlsx`)
- **Size:** 8,523 records, 12 columns
- **Columns:** Item Fat Content, Item Identifier, Item Type, Outlet Establishment Year, Outlet Identifier, Outlet Location Type, Outlet Size, Outlet Type, Item Visibility, Item Weight, Sales, Rating

## Data Cleaning (Power Query)
- Standardized inconsistent **Item Fat Content** labels: `LF` and `low fat` became **Low Fat**, and `reg` became **Regular** (5 labels reduced to 2).
- Checked data types and column quality before modeling.
- Noted that **Item Weight** has about 1,460 missing values; it is not used in the main KPIs.

## KPIs (DAX measures)
| KPI | Value |
|---|---|
| Total Sales | ~$1.20M |
| Average Sales per item | ~$141 |
| Number of Items | 8,523 |
| Average Rating | 3.9 |

## Dashboard Visuals
- Total sales by **item type** (bar chart)
- Sales split by **fat content** (donut chart)
- Sales by **outlet size** (donut chart)
- Sales by **outlet location tier** (funnel chart)
- Sales trend by **outlet establishment year** (line chart)
- Fat content vs location tier (clustered bar chart)
- **Outlet type** performance with total sales, average sales, items and rating (matrix)
- Interactive slicers: item type, outlet size, location tier and metric selector

## Key Insights
- **Fruits and Vegetables** (14.8%) and **Snack Foods** (14.6%) are the top-selling categories, together making up about 29% of sales.
- **Low Fat** items generate about **65%** of sales, versus 35% for Regular.
- **Tier 3** locations contribute the most sales (39%), ahead of Tier 2 (33%) and Tier 1 (28%).
- **Medium-sized** outlets lead with 42% of sales; High-sized outlets contribute only about 21%.
- **Supermarket Type 1** accounts for about **65%** of total sales, far ahead of the other outlet types.
- Seafood and Breakfast items have the lowest sales, a possible area to review.
- **Average sales per item is almost the same everywhere** (about $140–142) across outlet types, sizes and location tiers, and ratings are about 4.0 throughout. The leaders in total sales lead because they stock more items, not because each item sells better.

## Recommendations
1. Look at why Seafood (0.8% of sales) and Breakfast (1.3%) sell so little: range, pricing or placement.
2. Since sales per item are flat, grow sales by adding items and outlets in strong areas (Tier 3, Medium size), rather than expecting a particular outlet format to perform better.
3. Check why High-sized outlets bring in only about 21% of sales, and whether their space is being used well.
4. Track the 2018 outlet group, which stands out in the establishment-year chart (about $205K vs about $130K for most other years).

## Limitations
- The data has no dates for each sale, so there is no monthly trend or seasonality.
- It has no cost or profit data, so the analysis covers sales only, not profitability.
- `Item Weight` is missing in about 1,460 rows (17%) and was not used. `Item Visibility` is 0 for 526 items, which is probably missing data.
- Sales per record are similar across groups, so the totals mostly show how many records each group has.
- **Data source:** BlinkIT grocery sales dataset provided with the tutorial [Amazing Real Time Power BI Project | Start to End Analysis | Power BI For Beginners | Power BI 2024](https://youtu.be/mmxVCFceQgU?si=9gOJrkK1H8FgSwNV) by [Data Tutorials](https://www.youtube.com/@datatutorials1) on YouTube.

## What I added
I followed a Power BI tutorial for the dashboard build. On top of it, I wrote the business requirement breakdown, documented the data cleaning, checked the numbers in Python (including that average sales per item is nearly the same across outlet types, sizes and tiers), and wrote the insights, recommendations and limitations.

## Tools Used
Power BI Desktop, Power Query, DAX, Excel

## Repository Contents
| File | Description |
|---|---|
| `BlinkIT_Dashboard.pbix` | Power BI report (open in Power BI Desktop) |
| `BlinkIT_Grocery_Data.xlsx` | Source dataset |
| `Problem_Statement.pptx` | Business requirements and problem statements |
| `dashboard_screenshot.png` | Preview of the dashboard |

## How to Use
1. Download `BlinkIT_Dashboard.pbix` and `BlinkIT_Grocery_Data.xlsx`.
2. Open the `.pbix` file in Power BI Desktop.
3. If prompted, update the data source path to point to the Excel file.
4. Use the slicers to explore sales by item type, outlet size and location tier.

## Author
**VARSHINI GANESAN**: aspiring Data Analyst / Data Scientist
[LinkedIn](https://www.linkedin.com/in/varshiganesan) | [GitHub](https://github.com/vrshy)
