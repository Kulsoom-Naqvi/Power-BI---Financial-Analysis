# Power-BI Financial Analysis
📁 This project is an interactive Financial Data Analysis Dashboard built in Power BI Desktop, using the Finance_dataset.xlsx, as the single source of data. The goal was to take raw financial records and turn them into a clean, story-driven dashboard that a manager could glance at and instantly understand "how is the business doing?"

# 🗂️ Understanding the Data
The dataset has 700 rows and 16 columns. Each row represents one order of a product sold in a particular country and segment, on a specific date. The key columns are:

Segment – the type of customer the sale was made to (Government, Small Business, Enterprise, Midmarket, Channel Partners).
Country – where the order was placed (Canada, Germany, France, Mexico, USA, etc.).
Product – which product was sold (Paseo, VTT, Velo, Amarilla, Montana, Carretera).
Discount Band – how big a discount was given (High, Medium, Low, None).
Units Sold – how many units were sold in that order.
Manufacturing Price – the cost to manufacture one unit.
Sale Price – the price the unit was actually sold for.
Gross Sales – Units Sold × Sale Price (the revenue before any discount).
Discounts – the rupee/dollar amount knocked off because of the Discount Band.
Sales – Gross Sales minus Discounts (the actual revenue that came in).
COGS (Cost of Goods Sold) – this is the total cost incurred to produce/acquire the goods that were sold — basically Manufacturing Price × Units Sold. COGS tells us how much money was spent just to make the product before any selling, marketing, or admin costs.
Profit – Sales minus COGS. This is the money left over after covering production costs (the "bottom line" before other expenses).
Date / Month Number / Month Name / Year – when the order happened, used to build the time-based charts.

In short: Gross Sales → minus Discounts → = Sales → minus COGS → = Profit. Each row of data flows through this chain, and the dashboard rolls all 700 of these rows up into one story.

# 🖥️ Dashboard Walkthrough
# 1. Header – Branding & Navigation
At the top is a banner titled "Financial Data Analysis" with the Amazon logo on the left. The Amazon logo is set up as an image with a hyperlink/Q&A action, so clicking it takes the user directly to a website (Amazon.com) — this is the "Link to Website" requirement, giving the dashboard a real, clickable brand identity. 

# 2. KPI Cards (the "headline numbers")
Right under the header sit five Card visuals, each showing one big number — these are the dashboard's vital signs:
Sum of Sales – 118.73M: total revenue actually earned after discounts. This is the company's top-line income.
Sum of Profit – 16.89M: how much of that revenue turned into actual profit after covering production costs. Roughly 14% of sales converts to profit.
Sum of Discounts – 9.21M: how much revenue was given away through discounts. This shows how much "selling power" was sacrificed to win deals.
Sum of COGS – 101.83M: total cost of producing everything that was sold. Since COGS (101.83M) is the largest number on the page, it tells us production cost is by far the biggest expense driver.
Sum of Units Sold – 1.13M: total volume of products moved, regardless of price — a measure of business activity/scale.

Story so far: Out of every ~119 units of revenue earned, about 102 goes straight back into covering production costs, ~9 was given away as discounts, leaving roughly 17 as profit. This single row of cards instantly tells a viewer whether the company is healthy.

# 3. Combo Chart – "Sum of Sales, Sum of Gross Sales and Sum of Profit by Quarter"
Chart:
This is a clustered column and line combo chart built using Power BI's Date Hierarchy, allowing users to drill up or down between Year, Quarter, Month, and Day. The clustered columns compare Sales and Gross Sales, while the line represents Profit across different time periods.
Story:
The drill-down feature enables users to analyze financial performance at different levels of detail. They can view yearly and quarterly trends for a high-level overview or drill down to monthly and daily data to identify seasonal patterns, performance fluctuations, and periods of strong or weak business growth.

# 4. Donut Chart – "Sum of Sales by Product"
This chart breaks total sales down by each Product (Paseo, VTT, Velo, Amarilla, Montana, Carretera), showing both the value and percentage share for each:
Paseo – 33.01M (27.8%) — the best-selling product, more than a quarter of all sales.
VTT – 20.51M (17.28%)
Velo – 18.25M (15.37%)
Amarilla – 17.75M (14.95%)
Montana – 15.39M (12.96%)
Carretera – 13.82M (11.64%) — the smallest contributor.
Story: No single product dominates completely, but Paseo is clearly the flagship product, contributing nearly twice as much as Carretera, the weakest performer. This view helps a manager decide where to focus marketing or where a struggling product (VTT) might need attention.

# 5. Treemap – "Sum of Sales by Segment"
This visual uses rectangle sizes to represent how much Sales each customer Segment brought in (Government, Small Business, Enterprise, Midmarket, Channel Partners). The bigger the box, the higher the sales from that segment. In the screenshot, Government and Small Business are the largest blocks, meaning these two customer types are the biggest revenue contributors, while smaller segments like Enterprise occupy a much smaller area.
Story: This tells us who is buying — public-sector (Government) and small-business customers are the company's bread and butter, so any strategy around discounts, account management, or new product launches should keep these two groups front and center.

# 6. Line Chart – "Sum of Manufacturing Price and Sum of Sale Price by Year, Quarter, Month and Day"
This is a drill-down time series (it can be expanded from Year → Quarter → Month → Day) comparing two lines:
Sum of Manufacturing Price (cost side)
Sum of Sale Price (revenue side)
Both lines move almost in lockstep, with several sharp spikes throughout 2014 (visible peaks around certain months) and a baseline that hovers around 5K most of the time. The gap between the two lines represents the markup — how much extra is charged over the cost to manufacture.
Story: Because the two lines track each other so closely, pricing is consistently set as a fixed markup over manufacturing cost rather than fluctuating independently — useful for spotting any month where costs spiked without prices following (a red flag for shrinking margins).

# 7. Slicer – "Discount Band"
On the right is a checkbox-style slicer with four options: High, Low, Medium, None. This is the interactive filter of the dashboard — a user can tick one or more boxes (e.g. just "High") and every other visual on the page instantly updates to show only the sales/profit/cards/charts for orders that fell into that discount category. This lets a viewer answer questions like "How much profit do we lose specifically on heavily-discounted orders?" with a single click.

# 🔗 Putting it all together — The Story
The header tells you whose data this is (Amazon-branded) and gives you a way to navigate or jump to the live website.
The cards give the 10-second summary: how much we sold, what it cost us (COGS), how much we discounted, and what we kept as profit.
The quarterly chart shows when the money comes in — overwhelmingly in Q4.
The donut chart shows what sells — Paseo leads, VTT lags.
The treemap shows who buys — Government and Small Business dominate.
The price trend chart shows how pricing relates to cost over time.
The Discount Band slicer lets anyone dig deeper into how discounting strategy affects everything above.
