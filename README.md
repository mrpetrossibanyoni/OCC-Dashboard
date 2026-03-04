# OCC Dashboard – Operations Control Center (TFR)

## 📌 Overview
The OCC Dashboard is an enterprise-grade operational reporting dashboard developed for Transnet Freight Rail’s Operations Control Center. Its purpose is to provide **proactive, daily insight** into business performance across all six BUs:  
- Coal  
- Iron Ore  
- Mineral & Mining  
- Chrome  
- Manganese  
- Containers & Automotives  
- Steel & Cement  

The dashboard consolidates multiple operational KPIs and displays them through Power BI, using data sourced directly from SAP HANA CVD models.

## 🎯 Purpose  
The dashboard centralizes KPIs previously scattered across different systems (BOBJ, Power BI, TEMS) and standardizes reporting frequencies, enabling real-time monitoring and decision‑making.  

---

# 📊 Key Performance Indicators (KPIs)

### **1. Train Cancellations**
- YTD cancellations  
- Daily / Weekly / Monthly figures  
- Rolling 8‑week average  
- Top 3 cancellation reasons per BU  
- Excludes Schedule Type 3  
  

### **2. On‑Time Departures (OTD) & On‑Time Arrivals (OTA)**
- Daily, Weekly, Monthly, Yearly performance  
- OTD = On‑time departures / total departures  
- OTA = On‑time arrivals / total arrivals  
- Top 10 areas (best & worst)

### **3. Volume Performance**
- Daily, MTD, YTD actual vs budget tons  
- Next week’s business  
- Tempo required to meet budget

### **4. Revenue Performance**
- Daily, MTD, YTD, QTD revenue  
- Budget vs actual revenue  
- Variance and percentage variance  
- Tempo required to meet revenue budget

### **5. Train Compliance**
- Planned vs actual trains (daily, weekly, monthly)  
- Rolling 8‑week compliance  
- Top 10 / Bottom 10 areas

### **6. Train Capacity Utilization (TCU)**
- Daily, Weekly, Monthly TCU  
- TCU = Total Wagons / Wagon Design × 100  
- Top 10 / Bottom 10 areas  
- TCU by BU

### **7. Staged Trains**
- Total staged trains  
- Trains staged more than 5 hours  
- Staged trains by BU, Type, and Area  

---

# 🔧 Data Architecture

### **Data Sources (SAP HANA CVD Models)**
| KPI | Source CVD |
|-----|------------|
| Train Cancellations | CVD_OCC_MODEL, ZTFDS_CANCELLATION_ARC |
| Volume Performance | CVD_DAILY_REVENUE_PERFORMANCE |
| Revenue Performance | CVD_DAILY_REVENUE_PERFORMANCE |
| Train Compliance | CVD_TRAIN_COMLIANCE, CVD_CALENDAR |
| Train Capacity Utilization | CVD_TCU_UPDATED, CVD_CALENDAR |


### **Refresh Frequency**
- **Daily automatic ETL jobs** load SAP HANA → Power BI datasets.  
- Dashboard auto‑refreshes as part of the daily job.  

---

# 🛠️ Technology Stack
- **Power BI**
- **SAP HANA (CVD Models)**
- **ETL Jobs (Daily Scheduled Loads)**
- **Transnet Freight Rail Data Warehouse Ecosystem**

---

# 🧪 Test Plan Summary
- Validate daily data refresh  
- Validate correctness of KPI formulas  
- Verify accuracy of daily/weekly/monthly updates  
- Confirm BU filtering  
- Check last updated timestamps  

---

# 🔐 User Access
Users require **Power BI Production Access** through TFR intranet request forms.  
Reports accessible via Power BI Desktop, Service, and Mobile App.

---

# 📄 Documentation
This repository contains:
- Functional Specification (FS)
- Business rules & KPI formulas
- Data model mappings
- Test plan & validation documentation
- Dashboard assets (screenshots, PBIX file if allowed)

---


# 👤 Authors & Contributors
- **Business Owner:** Anele Maduna  
- **Business Analyst:** Ruth Legobate  
- **Lead Developer / YPT Contributor:** Petros Sibanyoni  
  *(Compliance reporting, KPI logic, dashboard build)*  

## 👥 Co‑Developers
- Katlego Serumula  
- Regomoditshwe Lebelela  
- Phathutsedzo Makala  
- Letago Mongale  
