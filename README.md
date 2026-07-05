# Collision-Analytics-Dashboard
📌 Overview

Road collisions are one of the leading causes of death and injury worldwide. This project analyzes real collision data from Great Britain covering 2021 and 2022, with over 300,000 accident records, to transform raw data into clear visual insights using Microsoft Power BI.

🎯 Key Objective

Primary KPIs


Total Casualties and Total Accidents for the current year, with Year-on-Year (YoY) growth comparison
Total Casualties by Accident Severity (Fatal, Serious, Slight) for the current year and YoY growth


Secondary KPIs


Total Casualties by vehicle type (Car, Bike, Bus, Van, Agricultural, Others) for the current year


Visual Requirements


Monthly trend: Current Year (CY) vs. Previous Year (PY) comparison
Casualties by road type
Casualties by area: Urban vs. Rural
Casualties by light condition (Day/Night)
Total casualties and accidents by location on map


🗂️ About the Dataset

The dataset contains 21 attributes, including:

Accident Date · Severity · Location (Latitude/Longitude) · Road Type · Speed Limit · Weather Conditions · Light Conditions · Vehicle Type · Number of Casualties · Number of Vehicles · and more

A separate Calendar table was also created to support time-based analysis.

🧹 Data Processing


Data Type Correction — Corrected data types for all columns: date columns set to Date type, numerical columns (Latitude, Longitude, Number of Casualties, etc.) set to Decimal/Whole Number, and text columns verified as Text type.
Handling Null Values — Identified rows with missing Latitude/Longitude; replaced missing values in categorical columns (Weather Conditions, Road Surface Conditions) with "Unknown" to avoid data loss.
Text Standardization — Standardized inconsistent text entries (e.g., grouped "Fine + high winds" and "Fine" under "Fine") and corrected spelling errors (e.g., "Fetal" → "Fatal").
Created Group Columns — Built new grouped columns for cleaner visualization:

Light Conditions (groups) — Day / Night
Vehicle Type (groups) — Car, Bike, Bus, Van, Agricultural, Others
Weather Conditions (groups) — Fine, Raining, Fog, Snow, Other
Road Surface Conditions (groups) — Dry, Wet, Snow/Ice



Calendar Table Creation — Built a separate Calendar table (Date, Month, Month Number, Year) connected to the main Data table via Accident Date to enable time-based filtering across all visuals.
DAX Measures Created — Custom measures for analysis:

CY Casualties (Current Year Casualties)
PY Casualties (Previous Year Casualties)
CY Accidents / PY Accidents
YoY Accidents % (Year-on-Year growth)
Fatal Rate %



Data Modeling — Verified a Many-to-One relationship between Calendar[Date] and Data[Accident Date] in Model View.
Final Validation — Cross-checked total casualty and accident counts against source data to confirm accuracy before building visuals.


📊 Dashboard Pages

Dashboard 1 — Overview


Total CY Casualties: 195.7K (-11.89% YoY)
Total CY Accidents: 144.4K (-11.70% YoY)
CY Fatal Casualties: 2.9K (-33.29% YoY)
CY Serious Casualties: 27.0K (-16.18% YoY)
CY Slight Casualties: 165.8K (-10.65% YoY)
Total PY Casualties: 222.1K | Total PY Accidents: 163.6K
Trend analysis of CY vs. PY casualties (monthly, Jan–Dec)
Casualties by Urban (61.95%) vs. Rural (38.05%) area
Casualties by light condition — Daylight (73.84%) vs. Darkness (26.16%)
Casualties by road type (Single carriageway, Dual carriageway, Roundabout, One-way street, Slip road)
Casualties by location, plotted on an interactive map of the UK


Dashboard 2 — Deep Dive


Casualties by vehicle type: Car (156K), Bike (16K), Van (16K), Bus (7K), Agricultural (399), Others (1K)
Speed limit vs. accident severity (Fatal, Serious, Slight)
Vehicle type vs. accident severity
Most dangerous districts: Birmingham, Leeds, Cornwall, Bradford, Liverpool
Weather and road surface conditions vs. accident severity (Fine, Fog, Other, Raining × Dry, Snow, Wet)
Accidents by day of week (Monday–Sunday), segmented by severity


🛠️ Tools Used


Microsoft Power BI — data modeling, DAX measures, and interactive visuals
Power Query — data cleaning and transformation
DAX — custom time-intelligence and KPI measures


👤 Author

Sakshi Maurya


This dashboard demonstrates end-to-end BI development: from raw data cleaning and modeling to building actionable, decision-ready visuals for road safety analysis.
