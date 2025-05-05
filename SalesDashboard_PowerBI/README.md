# 📘 Full Extended Documentation (EN)

This document contains a full breakdown of the **Sales Dashboard – Power BI Project**, covering data structure, transformations, DAX measures, and dashboard design decisions.

---

## 📌 Project Objective

To create an interactive sales dashboard in Power BI using a retail dataset.  
The dashboard provides management-level insight into sales performance across time, regions, and categories.

---

## 🗂️ Dataset Overview

- **Source**: [UCI Online Retail Dataset](https://archive.ics.uci.edu/ml/datasets/online+retail)
- **Fields used**:  
  - InvoiceNo  
  - StockCode  
  - Description  
  - Quantity  
  - InvoiceDate  
  - UnitPrice  
  - CustomerID  
  - Country

---

## 🔧 Power Query – Data Cleaning

Steps performed in Power Query:

1. **Filtered Quantity > 0**  
2. **Filtered UnitPrice > 0**  
3. **Removed nulls from InvoiceNo**  
4. **Created custom column `Sales` = Quantity × UnitPrice**  
5. **Extracted date parts**:  
   - Year  
   - Quarter  
   - Month (Name & Number)  
   - Day  
   - Weekday (Name)

---

## 🧠 DAX Measures

**1. Total Sales**
```DAX
Total Sales = SUM(SalesData[Sales])
```
**2. Orders Count**
```DAX
Orders Count = DISTINCTCOUNT(SalesData[InvoiceNo])
```
**3. Average Order Value**
```DAX
Average Order Value = DIVIDE([Total Sales], [Orders Count])
```
**4. Sales per Employee**
```DAX
Sales per Employee = DIVIDE([Total Sales], DISTINCTCOUNT(SalesData[Salesperson]))
```

## 📊 Dashboard Components

### 📌 KPI Cards
- Total Sales  
- Orders Count  
- Average Order Value (AOV)  
- Sales per Employee

### 📈 Visualizations
- Sales by Year / Quarter / Month (bar chart)  
- Top Products by Sales  
- Orders by Country  
- Sales by Category

### 🎛️ Slicers
- Month Name  
- Region / Country  
- Salesperson

## Author
Grzegorz Betyna
