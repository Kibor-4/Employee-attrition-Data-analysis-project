# 📊 Employee Attrition & Workforce Retention Analysis

## 📌 Executive Summary
Employee turnover introduces severe financial strains via recruitment costs, lost productivity, and diminished team morale. This project analyzes a corporate workforce dataset of **1,000 employees** to isolate the root causes of attrition and equip Human Resources with data-backed intervention strategies.

* **Business Problem:** The company is experiencing unmanaged employee turnover, driving up talent acquisition costs and threatening operational stability.
* **Objective:** Build an interactive HR intelligence dashboard to identify high-risk departments, evaluate compensation equity, uncover workplace stressors, and predict future attrition hotspots.
* **Core Deliverable:** A multi-page Power BI Interactive Dashboard comprising an *Executive Overview*, *Demographic Profiles*, and *Compensation & Performance Deep Dives*.

## 📂 Repository Structure
├── data/
│   └── employee_attrition_1000.csv  # Raw dataset containing 1,000 employee records
├── HR_Attrition_Dashboard.pbix      # Main Power BI Desktop file with data model & visuals
└── README.md                        # Executive analysis report (This file)

## 📊 Dashboard Preview
*Tip: Drag and drop a high-quality screenshot of your Power BI canvas right here to make your repository instantly scannable.*
![HR Dashboard Overview](link-to-your-uploaded-image.png)

## 🛠️ Data Transformation & Modeling (Power Query)
The raw dataset was imported, cleaned, and structurally optimized entirely within Power Query:
* **Conditional Attrition Flag:** Converted the text-based `Attrition` column ("Yes"/"No") into a binary integer format (`1` / `0`) to unlock advanced mathematical aggregations.
* **Age & Tenuring Brackets:** Grouped continuous numerical data into logical business categories (e.g., Age groups: `18-25`, `26-35`, `36-50`, `50+` and Tenure groups: `<1 Year`, `1-3 Years`, `3-5 Years`, `5+ Years`) to enable clean demographic filtering.
* **Data Hygiene:** Standardized departmental strings, validated data types, and confirmed that the dataset represents exactly **1,000 unique employee profiles**.

## 🧮 DAX Measures & Analytics Logic
To track organizational health efficiently, the following advanced DAX measures were engineered:

* **Total Attrition Headcount:** Counts the total number of employees who left the organization.
```dax
Total Attrition = CALCULATE(COUNT(employee_attrition_1000[EmployeeID]), employee_attrition_1000[AttritionFlag] = 1)
```

* **Attrition Rate (%):** Standardizes turnover metrics across departments regardless of staff size.
```dax
Attrition Rate % = 
DIVIDE(
    [Total Attrition], 
    COUNT(employee_attrition_1000[EmployeeID]), 
    0
)
```

* **Average Monthly Income:** Establishes a compensation baseline for equity analysis.
```dax
Avg Monthly Income = AVERAGE(employee_attrition_1000[MonthlyIncome])
```

## 📈 Executive Insights
Based on the visual data exploration of the 1,000-employee cohort, several critical retention vulnerabilities were identified:

Review overtime in Operations and Sales. Overtime is the clearest link to attrition, so set limits and check workloads.
Strengthen the first three years. Better onboarding, mentoring and promotion paths for new and early-career staff.
Target the under-25 group. Check pay, development and career pathways against what they leave for.
Look closer at employees rated 2. They show the highest attrition of any rating (21%), so see whether managers need support. 

## 💡 Strategic Recommendations
To actively lower the attrition rate and retain top talent, the following HR interventions are recommended:

| Priority | Strategy | Data-Backed Justification | Suggested Owner |
| :--- | :--- | :--- | :--- |
| **High** | **Overtime Cap & Compensation Restructuring:** Mandate strict caps on monthly overtime hours or introduce shift-differential premium pay. | Insight 1: Overtime workers leave at twice the organizational average rate. | Chief People Officer / Operations |
| **High** | **Enhanced 90-Day Onboarding:** Launch structured mentorship programs paired with mandatory 30, 60, and 90-day check-ins. | Insight 2: Severe turnover spike concentrated heavily in the first 24 months. | Talent Development Team |
| **Medium**| **Structured Career Paths:** Implement formal bi-annual talent reviews to ensure transparent, merit-based career progression. | Insight 4: Attrition surges significantly when promotions stagnate past year 3. | HR Business Partners |

## 🚀 How to Interact with this Project
1. Download and install the latest version of [Power BI Desktop](https://microsoft.com).
2. Clone this repository locally: `git clone https://github.com`
3. Open `HR_Attrition_Dashboard.pbix` in Power BI Desktop to interactively filter the visual matrix by Department, Role, and Tenure.

