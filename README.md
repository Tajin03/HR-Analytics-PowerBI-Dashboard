# Human Resources (HR) Analytics & Workforce Intelligence Dashboard

## 📊 Executive Project Summary
This enterprise-grade Power BI dashboard provides an interactive, data-driven framework for analyzing workforce demographics, tracking compensation structures, and isolating employee attrition drivers. By consolidating operational HR metrics, this business intelligence tool empowers HR leadership to optimize retention strategies, monitor departmental sentiment, and audit compensation equity.

## 🛠️ Data Architecture & Dimensions
The dashboard models multi-dimensional human resources data across several key analytical facets:
* **Demographics & Profile Filters:** Segmented by Gender (Male/Female) and Marital Status (Single, Married, Divorced).
* **Organizational Structure:** Hierarchical tracking across Key Departments (Human Resources, Research & Development, Sales) and 9 distinct Job Roles (including Sales Executives, Research Scientists, Laboratory Technicians, Managers, and Directors).
* **Education Profiles:** Analyzed across academic disciplines including Life Sciences, Medical, Marketing, Technical Degree, Human Resources, and Other.

---

## 📈 Dashboard Architecture & Visualizations

The reporting canvas is engineered using an intuitive grid layout structured into specialized analytical panes:

### 1. Workforce Mobility & Demographics
* **Travel Profile Breakdown:** A granular analysis tracking employee distribution against corporate travel frequencies (Travel_Rarely vs. Travel_Frequently).
* **Total Employee by Education Field:** Distribution maps charting the academic background density across the current headcount.

### 2. Sentiment & Workplace Experience
* **Role-Wise Workplace Satisfaction:** A multi-variable matrix correlating environmental satisfaction metrics directly against operational Job Roles to pinpoint localized cultural friction.
* **Job & Satisfaction Metrics by Education:** Cross-sectional analysis evaluating how an employee's educational discipline impacts their long-term engagement scores.

### 3. Compensation & Performance Auditing
* **Compensation & Salary Hikes by Role:** A dual-axis/hybrid chart tracking the correlation between overall compensation bands and the Average Salary Hike Percentage (ranging from 12.67% to 18.40% across specific roles).
* **Education Field Compensation Analysis:** Aggregated tracking of baseline financial allocations across employee academic backgrounds.
* **Highest Earning by Job Role:** Targeted tracking isolating top-tier income distribution across the organization's functional titles.

---

## 💡 Advanced Analytical Formulations (DAX)

To support the visual layer, advanced DAX measures were engineered to isolate early-tenure organizational risk rather than basic, non-specific turnover rates:

### Specialized Attrition Modeling
```dax
Positive Attrition Count = 
CALCULATE(
    SUM(HR_Analytics[EmployeeCount]),
    HR_Analytics[Attrition] = "Yes",
    HR_Analytics[YearsAtCompany] <= 2
)

Positive Attrition Rate = 
DIVIDE(
    [Positive Attrition Count], 
    SUM(HR_Analytics[EmployeeCount]), 
    0
)
