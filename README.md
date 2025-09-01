# Vilvah Retention Marketing Dashboard  

## 📌 Project Overview  
This project analyzes **customer retention performance** for **Vilvah**, a natural skincare and personal care brand. Using Power BI, the dashboard provides insights into customer behavior, retention trends, and KPIs to support data-driven decision-making.  

## 🛠 Tools & Technologies  
- **Power BI** – Dashboard creation and visualization  
- **Excel / CSV** – Data cleaning and preparation  
- **Power Query** – Data transformation  
- **Python (optional)** – Advanced preprocessing (if used)  

## 📊 Key Features of the Dashboard  
- **Executive Summary** highlighting retention performance.  
- **Line Chart** showing retention rate over time.  
- **Customer Segmentation KPIs** to track active customers and churn.  
- **Target vs. Actual Metrics** to assess goal achievement.  
- **Custom Branding** with Vilvah colors and logo for professional presentation.  

## 📈 KPIs Tracked  
1. **Active Customer Count** – How many customers are retained over time.  
2. **Retention Rate (%)** – Proportion of customers returning month-over-month.  
3. **Revenue from Returning Customers** – Measures loyalty impact on sales.  


---

## 🔄 Process Followed to Create the Worksheet  

1. **Data Collection**  
   - Raw data was exported from CRM/website tools (could later integrate HubSpot & Google Analytics).  
   - Files included **customer IDs, purchase dates, revenue, and demographics**.  

2. **Data Cleaning in Excel**  
   - Removed duplicates using:  
     ```excel
     =UNIQUE(A2:A1000)
     ```  
   - Filled missing values using conditional logic:  
     ```excel
     =IF(ISBLANK(B2),"Unknown",B2)
     ```  

3. **Cohort Grouping for Retention**  
   - Created a purchase month column using:  
     ```excel
     =TEXT(Purchase_Date,"MMM-YYYY")
     ```  
   - Grouped customers by first purchase month to track repeat activity.  

4. **Retention Rate Calculation**  
   - Counted customers retained in subsequent months using:  
     ```excel
     =COUNTIFS(Customer_ID_Range,Customer_ID,Month_Range,Target_Month)
     ```  
   - Retention % formula:  
     ```excel
     = (Retained_Customers / Original_Customers) * 100
     ```  

5. **Target vs Actual KPIs**  
   - Pulled retention targets from `vilvah_retention_targets.csv`  
   - Compared with actual retention using:  
     ```excel
     =Actual_Retention - Target_Retention
     ```  

6. **Dashboard in Power BI**  
   - Loaded cleaned Excel sheet into Power BI.  
   - Created **line charts** for retention trend, **cards** for KPIs, and **table visuals** for customer cohorts.  
   - Applied Vilvah branding (logo, theme colors).  

---

## 📊 Key Insights  
- **Month-over-month retention rate** highlighted where customer churn increased.  
- **Returning customers contributed significantly to revenue growth.**  
- **Specific cohorts showed strong loyalty**, suggesting targeted campaigns could further improve retention.  

---

## 📈 Formulas Used (Summary)  

- **Remove Duplicates:** `=UNIQUE()`  
- **Handle Missing Data:** `=IF(ISBLANK(cell),"Unknown",cell)`  
- **Create Cohorts:** `=TEXT(date,"MMM-YYYY")`  
- **Retention Count:** `=COUNTIFS()`  
- **Retention Rate:** `=(Retained / Base) * 100`  
- **Variance vs Target:** `=Actual - Target`  

---

## 🚀 How to Use  
```bash
# 1. Clone the repository
git clone https://github.com/your-username/vilvah-retention-dashboard.git

# 2. Navigate to the project folder
cd vilvah-retention-dashboard

# 3. Open vilvah_retention_workbook.xlsx to explore data preparation
# 4. Open vilvah_dashboard.pbix in Power BI Desktop to view dashboard
# 5. Refresh data to update metrics if sources are changed

