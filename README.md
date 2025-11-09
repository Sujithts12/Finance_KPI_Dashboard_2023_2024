# 💼 Finance KPI Dashboard 

A professional **Power BI dashboard** designed to analyze and monitor key financial performance indicators, including **Total Sales Actual vs Target**, **variance trends**, and **salesperson performance insights**.

## 🎥 [Watch the interactive video demo on LinkedIn] 
 - Link : [https://l1nk.dev/pHWeS](https://acesse.one/actual-vs-target-dataset)

📂 Download `.pbix` file and open it with **Microsoft Power BI Desktop**.  
👉 [Download Finance_KPI_Dashboard_2023_2024.pbix](https://github.com/Sujithts12/Finance_KPI_Dashboard_2023_2024/blob/main/Sales_And_Target_Analysis.pbix?raw=true)


## 📊 Overview  

The **Finance KPI Dashboard** provides a clear, interactive view of overall sales performance.  
It helps decision-makers identify underperforming areas, track progress toward goals, and make data-driven business decisions.

---

## 🧩 Key Features  

- **KPI Summary Cards**  
  - Total Sales Actual  
  - Total Sales Target  
  - Variance  
  - Month Target Reached  

- **Monthly Performance Chart**  
  Compare *Actual vs Target Sales* for each month with clear variance indicators.

- **Salesperson Performance Table**  
  Includes Actual, Target, % Variance, and individual trend (sparkline) visuals.

- **Dynamic Filters (Slicers)**  
  Teams (Select All, Delish, Juices, Tempo, Yummies).

- **Narrative Insights Panel**  
  Auto-generated text summarizing sales trends and key takeaways.
  
## 🧩 DAX Queries used
- **Total Sales Actual = SUM(Actual[Sales])
- **Total sales Target = SUM(Targets[Sales])
- **Varience = [Total Sales Actual]-[Total sales Target]
- **% Varience = DIVIDE([Varience],[Total sales Target])
- **Month Target Reached = VAR months_with_target_reached =FILTER('Calendar',[Varience]>0) RETURN COUNTROWS(months_with_target_reached)  
- **YTD sales Actual = CALCULATE([Total Sales Actual],DATESYTD('Calendar'[Date] ))
- **YTD Sales Target = CALCULATE([Total sales Target],DATESYTD('Calendar'[Date]))
- **Target Status = IF([Varience]>0,1,-1)

  - To make it completely static card visual(ignore all filters and slicers):

- Measure Actual static =
CALCULATE(
    SUM(Actual[Sales]),
    ALL()
)
- Measure Target static = 
CALCULATE(
    SUM(Targets[Sales]),
    ALL()
)
  - Dynamically change the Chart Title
- Trend Chart Title = 
VAR month_count = COUNTROWS('Calendar')
VAR reached = [Month Target Reached] RETURN
"We met target for " & reached & " out of " & month_count &
IF(month_count = 1, " month", " months")

  - for Stacked column chart
- Varience Pct Label = 
VAR up = "🟢"
VAR down = "🔴"
VAR neutral = "🟡"
VAR formatted_var_pct = FORMAT(ABS([% Varience]), "0.0%")
RETURN
formatted_var_pct &
IF([% Varience] > 0, up,
   IF([% Varience] < 0, down, neutral))
---
## 📊 Report Snapshot (Power BI DESKTOP)
1.
![Finance_KPI_Dashboard_2023_2024](https://raw.githubusercontent.com/Sujithts12/Sales_Analysis_Performance_USA/main/ALL.png)
2.
![Finance_KPI_Dashboard_2023_2024](https://raw.githubusercontent.com/Sujithts12/Sales_Analysis_Performance_USA/main/Delish.png)
3.
![Finance_KPI_Dashboard_2023_2024](https://raw.githubusercontent.com/Sujithts12/Sales_Analysis_Performance_USA/main/Jucies.png)
4.
![Finance_KPI_Dashboard_2023_2024](https://raw.githubusercontent.com/Sujithts12/Sales_Analysis_Performance_USA/main/Tempo.png)
5.
![Finance_KPI_Dashboard_2023_2024](https://raw.githubusercontent.com/Sujithts12/Sales_Analysis_Performance_USA/main/Yuminies.png)
# Data Model Snapshot 
![Finance_KPI_Dashboard_2023_2024](https://raw.githubusercontent.com/Sujithts12/Sales_Analysis_Performance_USA/main/sales1.jpeg)

---

# Report Snapshot (Power BI DESKTOP)

### 1. For All Teams
![Finance KPI Dashboard](https://raw.githubusercontent.com/sujithts31618-ui/Finance_KPI_Dashboard_2023_2024/main/IMG-20251102-WA0013.jpg)

### 2. For Team Delish
![Finance KPI Dashboard - Team Delish](https://raw.githubusercontent.com/sujithts31618-ui/Finance_KPI_Dashboard_2023_2024/main/IMG-20251102-WA0014.jpg)

### 3. For Team Juices
![Finance KPI Dashboard - Team Juices](https://raw.githubusercontent.com/sujithts31618-ui/Finance_KPI_Dashboard_2023_2024/main/IMG-20251102-WA0015.jpg)

### 4. For Team Tempo
![Finance KPI Dashboard - Team Tempo](https://raw.githubusercontent.com/sujithts31618-ui/Finance_KPI_Dashboard_2023_2024/main/IMG-20251102-WA0017.jpg)

### 5. For Team Yummies
![Finance KPI Dashboard - Team Yummies](https://raw.githubusercontent.com/sujithts31618-ui/Finance_KPI_Dashboard_2023_
## 🎨 Design Theme  

- **Color Scheme:**  
  - 🟩 Green → Target achieved / Positive variance  
  - 🟥 Red → Underperformance / Negative variance  
  - ⚪ Light Gray → Neutral visualization area
 
## 👨‍💻 Author
*Dashboard Created By:* Sujith TS 

*Date:* 2nd November 2025


## LinkedIn
 https://l1nk.dev/pHWeS

 ## 📌 Data Source Excel (actual-vs-target-dataset) attatched.



