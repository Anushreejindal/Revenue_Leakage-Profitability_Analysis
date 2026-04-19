# 🛒 Retail Performance Analysis – Superstore Insights

**Author**: Anushree Jindal <br>
**Dataset Used**: [Superstore Dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)

## 🛠️ Tools Used
- Power BI  
- Excel  

## 📌 Objective

To perform an end-to-end business performance analysis on retail data by evaluating sales, profit, discount patterns, and shipping methods. The goal is to identify inefficiencies and recommend strategies to improve profitability by reducing losses and enhancing operational effectiveness.

 
## 🧾 Understanding the Dataset
### 🚚 Ship Mode
Represents the shipping method chosen for each order. Since no official delivery timelines are provided, the following assumptions have been made:
 
| Ship Mode | Assumed Delivery Time | Cost Level | Notes |
|---|---|---|---|
| ⚡ Same Day | Same day | Highest | Can reduce profit due to high shipping costs |
| 🚀 First Class | 1–2 days | Moderate-High | Used for priority or urgent orders |
| 🚚 Second Class | 2–3 days | Medium | Balanced option, common in many businesses |
| 📦 Standard Class | 3–5+ days | Lowest | Ideal for bulk and cost-saving shipments |
 
### 👥 Segment
Represents the type of customer placing the order:

- Consumer - Individual customers buying for personal use
- Corporate - Companies or businesses buying in bulk
- Home Office - Small businesses or individuals working from home

### 🌍 Location Fields
| Column | Description |
|---|---|
| Country | Only one country present — not used in analysis |
| City | Exact customer location |
| State | Broader geographical unit (e.g., Texas, California) |
| Postal Code | Precise location identifier |
| Region | Group of states — West, East, Central, South |
 
### 📦 Product Fields
| Column | Description |
|---|---|
| Category | Broad product type - Furniture, Office Supplies, Technology |
| Sub-Category | Detailed product classification within each category |
 
### 💰 Financial Fields
| Column | Description |
|---|---|
| Sales | Revenue generated from the order (after discount applied) |
| Quantity | Number of units sold in the order |
| Discount | Discount offered on the product (in decimal form) |
| Profit | Actual profit or loss made on the order |

## 🛠️ Data Preparation
 
### Data Cleaning
- Checked for **duplicate values** in columns that should contain only unique entries (e.g., Order ID)
- Checked for **blank or null values** across all columns to ensure data completeness before analysis

### Feature Engineering
The following new columns were derived from existing data to enable more accurate and meaningful analysis:

- **Loss Column** — Isolates all negative values from the Profit column to separate losses from profit clearly.

- **Profit (Excluding Loss)** — Retains only positive profit values to enable true Profit vs Loss comparison without distortion.

- **Profit Margin** — Calculated as `Profit ÷ Sales` for margin analysis at category and subcategory level.

- **Profit Label** — Tags each row as *"Profit"* or *"Loss"* based on value sign, to simplify filtering during visual analysis.


## 📈 Insights from Analysis

### 🛍️ Product Analysis

#### 📊 Category-Level Insights
- **Technology** is the top-performing category with:
  - Highest sales contribution
  - Strongest profit and margins
  - Minimal losses

- **Office Supplies**
  - Stable revenue contributor
  - Moderate profit and margins
  - Losses ≈ 46% of profit → scope for optimization

- **Furniture**
  - Weakest category
  - Low profitability despite decent sales
  - High losses driven by heavy discounting


#### 🔍 Sub-Category Insights
- **Chairs** → High profit contributor (Furniture has potential)
- **Tables** → Major loss driver in Furniture
- **Binders** → Highest discount + highest losses


#### 🌍 Regional Category Insight
- **Central Region**
  - Only loss-making region for Furniture
  - Loss driven by Tables & Furnishings

- **West Region**
  - Most profitable

- **East Region**
  - Second-best performer


#### 💡 Discount Impact
- Strong inverse relationship:
  - Higher discount → Lower profitability
- Particularly severe in Furniture


> 🔑 **Key Insight (Product):**  
Profitability issues are concentrated in specific subcategories (e.g., Tables, Binders, Machines), not entire categories.  
High discounting is a major driver of these losses.


### 🌍 Region Analysis

#### 📊 Revenue & Profitability
- **West Region**
  - Highest revenue & profit
  - Most efficient

- **South Region**
  - Low profitability despite moderate sales


#### ⚠️ Problem Areas
- **Central Region**
  - Highest losses (~11.24% of sales)
  - Lowest profit margin
  - High discounting impacting performance


#### 👥 Segment Behavior
- In **West Region**:
  - Consumer → Main profit driver
  - Corporate → Strong secondary contributor


> 🔑 **Key Insight (Region):**  
Performance varies significantly by region.  
West excels due to efficiency, while Central underperforms due to discount-driven losses.


### 👥 Segment Analysis

#### 📊 Revenue & Profitability
- **Consumer**
  - Highest sales
  - Lower relative efficiency

- **Corporate & Home Office**
  - Lower sales
  - Better profit proportionality


#### 📈 Demand Behavior
- Consumer dominance driven by higher purchase volume


> 🔑 **Key Insight (Segment):**  
Consumer drives revenue, while Corporate and Home Office deliver better efficiency.  
Discount levels remain consistent across segments.


### 🚚 Ship Mode Analysis

#### 📊 Profitability & Volume
- **Standard Class**
  - Highest usage
  - Highest total profit (volume-driven)

- **Same Day**
  - Lowest usage
  - Lowest profit (high cost, low demand)


#### 📦 Segment Preference
- Standard Class → Most preferred across all segments
- Same Day → Least preferred consistently


> 🔑 **Key Insight (Shipping):**  
Shipping performance is driven by demand patterns.  
Standard Class dominates due to cost efficiency, while faster options see low adoption.


## ✅ Final Conclusion
The analysis reveals that profitability challenges are not widespread but concentrated in specific subcategories, regions, and operational decisions—particularly discounting strategies.  

Addressing high-discount, loss-making areas (like Tables and Binders) and improving regional efficiency (especially in Central) can significantly enhance overall business performance.
