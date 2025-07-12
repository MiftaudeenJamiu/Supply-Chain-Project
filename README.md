# Supply-Chain-Project

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning](#data-cleaning)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data analysis](data-analysis)
- [Visualisations and report](Visualisation-and-reports)
- [Results and Findings](#results-and-findings)
- [Conclusions](#conclusions)

### Project Overview
---
This project focuses on analysing key supply chain metrics across product, inventory, shipping, and manufacturing operations. Using Power BI, the dashboard provides visibility into product availability, order fulfilment, lead times, logistics costs, and profitability across different product types and SKUs. The aim is to identify process inefficiencies, track performance across supply nodes, and support data-driven decisions for supply chain planning and optimisation.

### Data Sources
The dataset was sourced from Kaggle and includes structured information on supply chain and logistics. The dataset covers multiple stages of the supply process, from procurement to delivery and post-inspection.
Key Fields in the Dataset:
- Product Details: Product Type, SKU, Price, Availability, Products Sold, Revenue
- Inventory & Stock: Stock Levels, Order Quantities, Lead Time, Manufacturing Lead Time
- Customer Data: Demographics for segmentation and sales pattern analysis
- Shipping Information: Shipping Times, Carriers, Costs
- Manufacturing: Manufacturing Cost, Inspection Results

### Tools
---
- Excel: Data Cleaning
- Power BI: Data Analysis and Visualisation

### Data Cleaning and Preparation
The dataset sourced from Kaggle was cleaned using Excel for initial review and Power Query in Power BI for transformation and modelling. The focus was on resolving missing values, normalising formats, and preparing the data model for analysis across inventory, sales, logistics, and manufacturing components.
- Initial Review (Excel):
1. Scanned for blank fields, invalid entries (e.g., negative lead times or costs), and duplicate SKUs.
2. Checked categorical fields (e.g., product type, carrier) for inconsistent naming.

- Missing Values
1. Replaced missing shipping times, lead times, and inspection results using average or mode values.
2. Removed rows with critical missing fields (e.g., SKU, product type) that could not be recovered.

- Format Standardisation
1. Converted date and numeric fields (e.g., lead time, cost, revenue) to proper data types.
2. Standardised text casing and spacing in product categories, shipping carriers, and inspection statuses.

- Derived Columns
1. Created Profit = Revenue – (MFG Cost + Shipping Cost)
2. Created Profit Margin % = (Profit / Revenue) × 100

- Grouped fields into categories for clearer analysis:
Lead Time Band (Short, Medium, Long)
Stock Level Category (Low, Medium, Overstocked)
Margin Category (High, Moderate, Low, Negative)

- Data Model Structure
Built a star schema in Power BI with: A central fact table for transactions and performance metrics
1. Dimension tables for products, customers, carriers, and dates
2. Defined one-to-many relationships using keys like SKU, Customer ID, and Carrier


### Exploratory Data Analysis
---
The EDA phase focused on understanding revenue patterns, cost contributors, inventory efficiency, and quality control across suppliers and products.

Key analysis areas included:
- Sales and Revenue Trends
Reviewed total products sold and revenue by SKU, product type, and consumer demographic to identify high-volume and high-value segments.
- Cost Breakdown
Evaluated manufacturing, shipping, and total costs by SKU and supplier. Flagged items with high cost-to-revenue ratios and reviewed margin volatility.
- Stock and Inventory
Assessed stock levels and order quantities across SKUs. Identified products with low inventory but high demand, as well as overstocked low-selling items.
- Lead Times and Fulfilment
Analysed average and maximum lead times by SKU to surface slow-moving products and supplier bottlenecks.
- Quality and Defect Rates
Explored inspection outcomes and defect percentages across product types and transportation modes. Products with high defects were tagged for deeper review.

These insights shaped the structure and focus of the dashboard: profit margins, inventory health, and supplier performance.

### Visualisation and Reports

The Power BI dashboard was organised across three key report pages: Overview, Product Analysis, and Supplier Analysis.
- Overview Page
1. KPI Cards: Total Revenue, Total Products Sold, Total Costs, Average Profit Margin %, Total Stock Level
2. Segment Analysis: Total Revenue by Consumer Demographics, Total Revenue by Product Type, Total Revenue by Shipping Carrier, Total Revenue by SKU, Average Defect Rate by Product Type
3. Supplier Table: A ranked table displaying Supplier Name and Average Profit Margin %, allowing fast identification of low-margin suppliers.
See the snapshots below for an overview of the Overview Page.

<img width="1202" height="667" alt="Screenshot 2025-07-11 211914" src="https://github.com/user-attachments/assets/60f18b27-d85c-41ec-b29c-9b138f9f0299" />


- Product Analysis Page
1. Order Quantity vs. SKU: Bar chart comparing sales volume by SKU.
2. Stock Level vs. SKU: Inventory monitoring to identify overstocked or understocked items.
3. Lead Time vs. SKU: Highlights fulfilment delays or variability across SKUs.
4. Avg Profit Margin% % by Product Type: Displays profitability at the category level.
5. Scatter Plot – Products Sold by SKU: Helps spot high-selling vs. low-moving products and correlates with inventory and cost patterns.
See the snapshots below for an overview of the Product Analysis Page.

<img width="1198" height="667" alt="Screenshot 2025-07-11 211859" src="https://github.com/user-attachments/assets/f4308b49-2da3-4b8f-ba78-6af37a07f15b" />


- Supplier Analysis Page
1. Total Costs by Transportation Mode: Evaluates logistics expenses by mode (e.g., air, sea, ground).
2. Avg Defect Rate by Transportation Mode: Links shipping methods to quality issues.
3. Supplier Cost Breakdown: Shows total cost, manufacturing cost, and shipping cost by supplier.
4. Scatter Plot – Supplier vs. Profit Margin & Defect Rate
Plot suppliers by total profit margin and defect rate, identifying suppliers that are either profitable or problematic (or both).
See the snapshots below for an overview of the Supplier Analysis Page.

<img width="1198" height="666" alt="Screenshot 2025-07-11 211843" src="https://github.com/user-attachments/assets/628dd3bb-f480-4e56-b6e4-1fd5c077eb52" />


### Results and Findings 
---
The dashboard revealed several important patterns:
- Revenue concentration: A small number of SKUs drive a large share of total revenue. These SKUs also show higher defect rates, indicating a risk to high-value inventory.
- Low-margin suppliers: Several suppliers have negative or near-zero average profit margins while maintaining high shipping and manufacturing costs.
- Defect-prone transport modes: Products shipped via specific transportation modes (e.g., air or certain regional carriers) showed consistently higher defect rates.
- Inventory issues: A mismatch was found between stock levels and order volumes for several SKUs. Some low-demand products are overstocked, while top-selling products face stock shortages and long lead times.

### Conclusions 
---
This supply chain analysis project used Power BI to evaluate performance across sales, inventory, shipping, and supplier operations. The dashboard helps track key metrics like revenue, cost, profit margin, and defect rate across multiple dimensions.

The findings support actionable improvements in:
1. Inventory planning (e.g., balancing stock against demand)
2. Supplier evaluation (e.g., cutting low-margin, high-defect vendors)
3. Logistics decisions (e.g., optimising transportation modes based on defect and cost impact)
This end-to-end report provides the operations team with the tools needed to reduce costs, improve margins, and manage supply risk with data-backed decisions
