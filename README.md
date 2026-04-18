# 🏥 Healthcare Data Analysis 


## 📑 Table of Contents

1. Project Overview  
2. Dataset Description   
3. Data Preparation & Transformations  
4. DAX Measures  
5. Key KPI Measures  
6. Branch / Location Measures  
7. Dashboard Pages & Visualizations     
8. Drill-Down & Interactivity  
9. Performance Optimization  
10. How to Reproduce / Deliverables  
11. Business Insights
12. Conclusion
13. Dashboard Images

---


# 📌 1. Project Overview

This project focuses on analyzing hospital data to generate insights related to:

- 🏥 Patient admissions and discharges  
- 💰 Hospital revenue  
- 👨‍⚕️ Department performance  
- ⏳ Patient stay duration  

### 🎯 Objective:
To improve **hospital efficiency, patient care, and financial performance** using data-driven insights.

---

# 📊 2. Dataset Description

The dataset contains hospital operational and patient data:

| Column Name        | Description |
|-------------------|------------|
| Patient_ID        | Unique patient identifier |
| Patient_Name      | Name of patient |
| Age               | Patient age |
| Gender            | Male / Female |
| Admission_Date    | Date of admission |
| Discharge_Date    | Date of discharge |
| Department        | Hospital department |
| Doctor            | Assigned doctor |
| Treatment_Cost    | Cost of treatment |
| Payment_Status    | Paid / Pending |
| City              | Patient location |

---


# 🧹 3. Data Preparation & Transformations

## Step 1: Data Cleaning
- Removed null values  
- Removed duplicates  
- Standardized column names  

---

## Step 2: Data Type Conversion
- Converted Transaction_Date to datetime  
- Ensured numeric columns  

---

## Step 3: Feature Engineering

### Length of Stay
```python id="h1"
df['Stay_Days'] = (df['Discharge_Date'] - df['Admission_Date']).dt.days
```
### Extract Date Features
df['Year'] = df['Admission_Date'].dt.year
df['Month'] = df['Admission_Date'].dt.month

## Step 4: Data Validation
- Checked balance consistency
- Verified discharge dates > admission dates


---
##  📐 4. DAX Measures (Power BI)
- ### Total Patients
Total Patients = DISTINCTCOUNT('Hospital'[Patient_ID])
- ### Total Revenue
Total Revenue = SUM('Hospital'[Treatment_Cost])
- ### Average Stay
Avg Stay = AVERAGE('Hospital'[Stay_Days])
- ### Payment Pending
- Pending Payments = 
COUNTROWS(FILTER('Hospital','Hospital'[Payment_Status]="Pending"))

---
# 📊 5. Key KPI Measures
- 👥 Total Patients
- 💰 Total Revenue
- ⏳ Average Stay Duration
- ❗ Pending Payments
---

# 📍 6. Branch / Location Measures

- ### Department / Location Measures
- Patients by Department
  Department Patients = COUNT('Hospital'[Department])
- Revenue by Department
  Department Revenue = SUM('Hospital'[Treatment_Cost])

# 📊 7. Dashboard Pages & Visualizations

## 1️⃣ Overview Dashboard

### KPIs:

- Total Patients
- Revenue
- Avg Stay
- Pending Payments

### Charts:

- Admission trend
- Gender distribution

## 2️⃣Patient Analysis

### Charts:

- Age distribution
- Patient demographics

## 3️⃣Department Analysis

### Charts:

- Patients by department
- Revenue by department

## 4️⃣Revenue Analysis

### Charts:

- Monthly revenue trend
- Payment status
---
# 🔍 8. Drill-Down & Interactivity

### Drill-Down:
- Year → Month 
- Department → Doctor
### Filters:
- Department
- Payment Status
- Date
### Interactivity:
- Cross-filtering
- Dynamic visuals

---
# ⚡ 9. Performance Optimization
- Removed unused columns
- Optimized DAX calculations
- Reduced visual load
---

# 🚀 10. How to Reproduce / Deliverables
### Steps:
- Load dataset into Power BI / Python
- Clean and transform data
- Create calculated columns
- Build dashboard

### 📦 Deliverables
- ✅ Power BI Dashboard (.pbix)
- ✅ Python Notebook (.ipynb)
- ✅ Dataset
- ✅ Insights


# 📈 11. Business Insights

- 🏥 Certain departments handle more patients
- 💰 Revenue varies across departments
- ⏳ Longer stays increase costs
- ❗ Pending payments impact cash flow
---

# ⭐12. Conclusion

This project demonstrates:
- End-to-end healthcare data analysis
- Dashboard design using Power BI
- Strong analytical and business insight skills

---

# 💡13.Dashboard Insight Chart Wise
## A) Excel
### 1)Chart Type: Column chart
- Insight: Patients by department.
- Minimum count of patients : 14135 and Department : Cardiology
- Maximum count of patients : 14438 and Department : Oncology

### 2) Chart Type : Bar chart
- Insight: Total cost by department
- Minimum cost : 1426710213 and Department : Pediatrics
- Maximum cost : 1452499162 and Department : Oncology

### 3) Chart Type: 100% stacked column
- Insight: Gender distribution per department
- Male: Minimum patient count : 4742 and Department : Pediatrics
- Male: Maximum patient count : 4875 and Department : Oncology
- Female: Minimum patient count : 4667 and Department : Cardiology
- Female: Maximum patient count : 4824 and Department : Oncology
- Other: Minimum patient count : 4705 and Department : Cardiology
- Other: Maximum patient count : 4783 and Department : Neurology

### 4) Chart Type: Column chart
- Insight: Patient count by month
- Minimum patient : 7942 and Month : Feb
- Maximum patient: 8613 and Month: Mar

### 5) Chart Type: Line chart
- Insight: Monthly discharge trend
- Minimum count of patient: 7737 and Month :Feb 
- Maximum count of patient : 8666 and Month : Mar

### 6) Chart Type: Pie chart
- Insight: Blood type distribution
- Minimum count of patient :12357 and Blood group : AB+
- Maximum count of patient : 12610 and Blood group : B-

### 7) Chart Type: Column chart
- Insight: Top 10 doctors with highest patient count
- Minimum patient count: 27 and Doctor name: David Smith, James Johnson, Jessica Smith
- Maximum Patient count: 42 and Doctor name: Michael Johnson


### 8) Chart Type: Pie Chart
- Insight: Admission type distribution
- Minimum patient count: 33244(33%) and Admission type: Elective
- Maximum patient count: 33472(34%) and Admission type: Maternity

### 9) Chart Type: Clustered Column
- Insight: Diagnosis wise patient distribution
- Cancer minimum patient count: 4161 and Gender: Female
- Cancer maximum patient count: 4209 and Gender: Other
- Diabetes minimum patient count: 4021 and Gender: Female
- Diabetes maximum patient count: 4226 and Gender: Other
- Epilepsy minimum patient count: 4113 and Gender: Female
- Epilepsy maximum patient count: 4160 and Gender: Other
- Fracture minimum patient count: 4035 and Gender: Other
- Fracture maximum patient count: 4288 and Gender: Male
- Hypertension minimum patient count: 4130 and Gender: Other
- Hypertension maximum patient count: 4194 and Gender: Female
- Infection minimum patient count: 4156 and Gender: Female
- Infection maximum patient count: 4196 and Gender: Male
- Pregnancy minimum patient count: 4152 and Gender: Male
- Pregnancy maximum patient count: 4197 and Gender: Female
- Stroke minimum patient count: 4128 and Gender: Other
- Stroke maximum patient count: 4235 and Gender: Female

### 10) Chart Type: Clustered Column
- Insight: Department wise patient status
- Pediatrics minimum patient count: 4709 and Status: Transferred
- Pediatrics maximum patient count: 4787 and Status: Admitted
- Orthopedic minimum patient count: 4727 and Status: Transferred
- Orthopedic maximum patient count: 4822 and Status: Admitted
- Oncology minimum patient count: 4750 and Status: Discharged
- Oncology maximum patient count: 4932 and Status: Admitted
- Neurology minimum patient count: 4726 and Status: Transferred
- Neurology maximum patient count: 4906 and Status: Discharged
- General Medicine minimum patient count: 4706 and Status: Admitted
- General Medicine maximum patient count: 4780 and Status: Transferred
- Emergency minimum patient count: 4742 and Status: Transferred
- Emergency maximum patient count: 4795 and Status: Admitted
- Cardiology minimum patient count: 4668 and Status: Transferred
- Cardiology maximum patient count: 4809 and Status: Admitted

### 11) Chart Type: Pie Chart
- Insight: Gender distribution
- Minimum patient count: 33225(33%) and Gender: Other
- Maximum patient count: 33496(34%) and Gender: Male

### 12) Chart Type: Line Chart
- Insight: Admission wise patient count
- Maternity minimum count: 2745 and Month: April
- Maternity maximum count: 2887 and Month: May
- Emergency minimum count: 2573 and Month: Feb
- Emergency maximum count: 2881 and Month: March
- Elective minimum count: 2606 and Month: Feb
- Maternity minimum count: 2942 and Month: Dec

## B)Microsoft Power Bi:
### 1) Chart Type: Bar chart
- Insight: Patient by department 
- Minimum patient count :14135 and Department: Cardiology
- Maximum patient count :14438 and Department: Oncology

### 2) Chart Type: Line chart
- Insight: Admission trend by month
- Minimum patient count :7942 and Month: February
- Maximum patient count: 8613 and Month: March

### 3) Chart Type: Donut chart
- Insight: Department wise amount paid
- Minimum paid amount :$1.07 bn (14.15%) and Department: Pediatrics
- Maximum paid amount: $1.09 bn (14.49%) and Department: Oncology 

### 4) Chart Type: Stacked column chart
- Insight: Procedure and lab tests count
- Minimum procedure count :35233 and Department: Cardiology
- Maximum procedure count:36454 and Department: Oncology
- Minimum lab test count: 56563 and Department: Cardiology
- Maximum lab test count: 58099 and Department: Oncology

### 5) Chart Type: Donut chart
- Insight: Sum of total bill amount by gender  
- Minimum total bill amount: $3342322701.02(33.22%) and Gender: Other
- Maximum total bill amount: $3362526462.45(33.42%) and Gender: Male

### 6) Chart Type: Clustered bar chart
- Insight: Count of is prepaid id by diagnosis
- Minimum count of is prepaid :12428 and Diagnosis: Diabetes
- Maximum count of is prepaid :12572 and Diagnosis: Cancer

### 7) Chart Type: Donut chart
- Insight: Gender Distribution
- Minimum patient count: 33225(33.23%) and Gender: Other
- Maximum patient count: 33496(33.5%) and Gender: Male

### 8) Chart Type: Stacked column chart
- Insights: Average of length of stay by department
- Minimum avg length of stay: 15.44 and Department: General Medicine
- Maximum avg length of stay: 15.63 and Department: Emergency

### 9) Chart Type: Scatter Chart
- Insights: Medical workload per patient
- Minimum sum of procedure count: 35540 and Department: Pediatrics
- Maximum sum of procedure count: 36155 and Department: General Medicine
- Minimum sum of lab test count:56563 and Department: Cardiology
- Maximum sum of lab test count: 57584 and Department: Neurology
- Minimum medication count: 77634 and Department: Emergency
- Maximum medication count: 78872 and Department: Neurology

### 10) Chart Type: Stacked bar chart
- Insights: Top 10 highest paying patient 
- Minimum total bill amount: $199978.22 and Patient ID: P020662
- Maximum total bill amount: $199995.58 and Patient ID: P098777


### 11) Chart Type: Donut chart
- Insights: Count of patient id by payment mode
- Minimum patient id count: 19800(19.8%) and Payment mode: Insurance
- Maximum patient id count:20227(20.23%) and Payment mode: Credit Card

### 12) Chart Type: Area chart
- Insights: Revenue trend over time 
- Minimum total bill amount: $26055396.5 , Payment mode: UPI and Month: 2023 June 
- Maximum total bill amount: $8889787.7 ,Payment mode: UPI and Month: 2024March 
- Minimum total bill amount: $28010789.7, Payment mode: Insurance and Month: 2023 June 
- Maximum total bill amount: $87917663.1Payment mode: Insurance and Month: 2024July
- Minimum total bill amount: $28871163.55, Payment mode: Debit card and Month: 2023June 
- Maximum total bill amount: $91280772.51, Payment mode: Debit card and Month: 2024May
- Minimum total bill amount: $29920354.85,Payment mode: Credit card and Month: 2023June 
- Maximum total bill amount: $91031329.65,Payment mode: Credit card and Month: 2023July
- Minimum total bill amount: $30607193.55,Payment mode: Cash and Month: 2023June 
- Maximum total bill amount: $94900287.82,Payment mode: Cash and Month: 2023October

# C) Tableau Public Edition 

### 1) Chart Type: Line chart
- Insight: Admission Trend
- Minimum patient count :7942 and Month: February
- Maximum patient count: 8613 and Month: March

### 2) Chart Type: Stacked bar chart 
- Insight: Patients by department
- Minimum patient count :14135and Department: Cardiology
		         (Female: 4667, Male: 4763, Other: 4705)
- Maximum patient count :14438 and Department: Oncology
		          (Female: 4824, Male:4875, Other:4739)

### 3) Chart Type: Pie chart
- Insight: Payment mode distribution
- Minimum amount paid: 1493146017 and Payment mode: Debit card
- Maximum amount paid: 1528688250 and Payment mode: Credit card

### 4) Chart Type: Packed bubbles
- Insight: Medication count analysis
- Minimum medication count(bin): 0 and Count of medication : 10057
- Maximum medication count(bin): 6 and Count of medication: 19771

### 5) Chart Type: Horizontal bar chart
- Insight: Top 10 high-bill patients
- Minimum bill amount: 199978.22 and Patient ID: P020662 
- Maximum bill amount: 199995.58 and Patient ID: P098777

### 6) Chart Type: Treemap chart
- Insight: Top 10 insurance provider
- Minimum outstanding amount: 2367925 and Insurance provider: Johnson Ltd
- Maximum outstanding amount: 3068457 and Insurance provider: Smith LLC

### 7) Chart Type: Horizontal bars
- Insight: Procedure vs lab test by department
- Minimum lab test count: 56563 , Procedure count: 35233 and Department: Cardiology
- Maximum lab test count: 58099 , Procedure count: 36454 and Department: Oncology

### 8) Chart Type: Stacked bar chart
- Insight: Revenue by department
- Minimum revenue: 1067635620.81 and department: Pediatrics 
  (Cash: 211610657.05, Credit card: 212164870.23, 
- Debit card: 219253664.19, Insurance: 211093293.86, UPI: 213513135.48)
- Maximum revenue: 1093238438.6 and department: Oncology
  (Cash: 221795970.25, Credit card: 224896597.23, 
- Debit card: 220021291.97, Insurance: 214653531.08 UPI: 211871048.07)

### 9) Chart Type: Horizontal bars
- Insight: Gender wise avg length of stay
- Minimum avg length of stay: 15.49983 and Gender: Other
- Maximum avg length of stay: 15.51564 and Gender: Male

### Excel Dashboard
<img src="https://github.com/GauriPise/Hospital-Data-Analysis/blob/main/Picture1.png" width="1000"> <br> 

---
### Power BI Dashboard
<img src="https://github.com/GauriPise/Hospital-Data-Analysis/blob/main/Picture2.png" width="1000"> <br> 

---

### Tableau Dashboard
<img src="https://github.com/GauriPise/Hospital-Data-Analysis/blob/main/Picture3.png" width="1000"> <br> 
