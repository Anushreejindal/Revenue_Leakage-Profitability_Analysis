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

## 📊 Key Insights

### 🗂️ Product Analysis

- **Technology** is the top performing category — highest sales, strongest profit margins, minimum losses.
- **Office Supplies** is a stable revenue driver but losses account for ~46% of its profit.
- **Furniture** is the weakest category — low profits due to heavy discounting and high losses.
- Not all Furniture products are loss making — **Chairs** ranks among the **Top 10 most profitable subcategories** company-wide.
- **Tables** is the single biggest problem within Furniture — removing Tables significantly improves the category's overall profitability.
- Clear inverse relationship found between **discount and profit** — higher discounts consistently lead to lower profitability.
- **Binders** holds the highest average discount and is simultaneously the most loss making subcategory — discount is a direct driver of losses.

> 💡 Losses are not spread across entire categories but concentrated in specific subcategories, driven primarily by heavy discounting.

---

### 🌍 Region Analysis

- **West** is the most efficient region — highest revenue, highest profit, controlled losses.
- **South** is the least profitable region despite moderate sales.
- **Central** appears to be a loss making region overall — but drilling down reveals that only **2 out of 12+ states** are responsible for the entire region's losses. The rest of the region is profitable.
- Central's losses are largely driven by **high average discounts** eroding its profit margin.

> 💡 Writing off an entire region based on surface level numbers would be misleading — the problem is concentrated in just 2 states.

---

### 👥 Segment Analysis

- **Consumer** segment drives the highest sales and profit but is less efficient — profit is not proportional to its revenue share.
- **Corporate and Home Office** generate lower sales but achieve more proportionate profit — better efficiency per sale.
- Discount levels are consistent across all segments — discounting is not a differentiating factor between customer types.

> 💡 High volume does not always mean high efficiency — Corporate and Home Office outperform Consumer in profit proportionality.

---

### 🚚 Ship Mode Analysis

- **Standard Class** dominates in both order volume and profit — but this is a volume effect, not an efficiency indicator.
- **Same Day delivery** contributes minimally due to low demand and higher shipping costs eating into margins.
- Standard Class is the most preferred and Same Day the least preferred shipping mode across all three customer segments.

> 💡 Shipping mode performance is driven by customer preference, not operational efficiency.

---

## ✅ Final Conclusion
The analysis reveals that profitability challenges are not widespread but concentrated in specific subcategories, regions, and operational decisions—particularly discounting strategies.  

Addressing high-discount, loss-making areas (like Tables and Binders) and improving regional efficiency (especially in Central) can significantly enhance overall business performance.
