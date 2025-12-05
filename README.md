# Hospital Visit Performance Data Analysis Dashboard

## Project Overview
The Hospital Visit Performance Dashboard is an end-to-end healthcare analytics project built using Microsoft Power BI. The purpose of this project is to analyze patient visits, revenue trends, diagnosis patterns, department performance, demographic breakdowns, doctor workload, and payment insights for a multispeciality hospital.

This project demonstrates how raw healthcare data can be transformed into meaningful insights using Power Query, DAX, data modeling, and modern Power BI visual design. The final dashboard supports data-driven decision-making for improving hospital operations, staffing, and patient care quality.

---

## Dashboard

<img src="https://github.com/omkarshinde25/Hospital-Visit-Performance-Dashboard/blob/main/Dashboard/Hospital%20Visit%20Performance%20Dashboard.png" width="800">

---

## Key Insights
1. Gynecology has the highest patient visits, mainly due to heavy outpatient demand.
2. Viral Infection contributes the highest revenue among all diagnoses.
3. Mumbai records the maximum patient visits across all cities.
4. Females dominate visits in Gynecology; middle-aged groups show the highest frequency of visits.
5. Doctor workload is uneven, with a few top doctors handling most patient cases.
6. Seasonal patterns show higher hospital visits during monsoon and winter months.
7. Older adults incur the highest treatment cost due to complex medical requirements.
8. Credit Card is the most preferred payment method followed by Insurance.
9. A moderate positive relationship exists between patient age and treatment cost.

---

## Step 1: Dataset Overview
The dataset consists of 10,000 synthetic patient visit records representing real-world hospital activity.

### Dataset Fields
- Patient ID  
- Age  
- Gender  
- City  
- Department  
- Diagnosis  
- Doctor  
- Visit Date  
- Treatment Cost  
- Payment Method  
- Symptoms  

**Total Records:** 10,000  
**File Type:** CSV  

---

## Step 2: Data Cleaning and Transformation (ETL)
Performed using Power Query Editor in Power BI.

### Key Transformations
- Removed null and duplicate records  
- Standardized text fields (department, city, diagnosis)  
- Converted data types (date, numeric, categorical)  
- Extracted Year, Month, Quarter from Visit Date  
- Created Age Groups: Child, Adult, Middle-aged, Senior  
- Trimmed spaces and corrected formatting issues  
- Ensured consistent naming conventions  

---

## Step 3: Data Modeling and DAX Calculations
A clean star-schema data model was created with:
- Fact Table: hospital_visits  
- Dimension Table: Calendar  
- Relationships based on Visit Date  

### Example DAX Measures
```DAX
Total Visits = COUNT(hospital_visits[PatientID])

Total Revenue = SUM(hospital_visits[TreatmentCost])

Total Patients = DISTINCTCOUNT(hospital_visits[PatientID])

Average Cost Per Visit = DIVIDE([Total Revenue], [Total Visits])

Visits LY = CALCULATE([Total Visits], SAMEPERIODLASTYEAR(Calendar[Date]))

Revenue by Department =
    CALCULATE(
        [Total Revenue],
        ALLEXCEPT(hospital_visits, hospital_visits[Department])
    )
```
## Step 4: Dashboard Design and Development

### Visual & UI Design Elements
- Clean hospital-themed color palette (blue, white, gray)
- KPI cards for summary metrics
- Separate sections for trends, departments, demographics, and payments
- Slicers for Year, Gender, Department, and City
- Consistent layout, spacing, and typography for clarity

---

## Step 5: Visualizations Created
- KPI Cards: Total Patients, Total Visits, Total Revenue, Avg Cost
- Line Charts: Monthly Visits Trend, Monthly Revenue Trend
- Bar/Column Charts:
  - Revenue by Department
  - City-wise Visits
  - Diagnosis distribution
- Pie Chart: Gender Breakdown
- Map Chart: City-wise Patient Spread
- Heat Map: Age Group vs Department activity
- Scatter Plot: Age vs Treatment Cost
- Table: Top Doctors by Visit Volume

---

## Step 6: Insights and Findings
- Gynecology and Orthopedics are the busiest departments.
- Viral Infection and Chronic Pain generate the maximum revenue.
- Middle-aged adults contribute the highest visit volume.
- Male vs Female visit ratios vary significantly by department.
- Doctor workload is concentrated among a few high-performing doctors.
- Seasonal illness patterns strongly influence visit trends.
- Credit Card and Insurance dominate payment preferences.
- Senior citizens show the highest average treatment cost.

---

## Step 7: Tools and Technologies Used
- Power BI
- Power Query (ETL)
- DAX
- Star Schema Modeling
- Excel / CSV Dataset

---

## Step 8: Project Outcome
This dashboard helps hospital leadership:
- Identify high-performing and low-performing departments
- Understand patient demographics for better planning
- Monitor revenue and seasonal visit trends
- Evaluate doctor workload distribution
- Improve decisions related to staffing, budgeting, and patient services

---

## Step 9: How to Use
1. Open the file “Hospital Visit Performance.pbix” in Power BI Desktop  
2. Load the dataset into the model  
3. Use slicers for Year, Department, Gender, City  
4. Navigate through dashboard sections to explore insights  

---

## Step 10: Key Learning and Skills Demonstrated
- End-to-end data cleaning and ETL using Power Query  
- Advanced DAX measures and KPI creation  
- Building star-schema models for analytics  
- Designing professional Power BI dashboards  
- Storytelling using healthcare analytics  
- Interpreting operational insights from real-world datasets  

---

## Conclusion
This project demonstrates the complete BI workflow: data extraction, cleaning, modeling, calculation, visualization, and insight creation. It shows how Power BI can convert raw hospital data into actionable intelligence for operational and strategic decision-making in the healthcare industry.

