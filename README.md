# Healthcare - Emergency Room Visits Dashboard


## Problem Statement

This dashboard provides an overview of Emergency Room (ER) patient visits, focusing on key operational metrics and patient demographics. It helps healthcare administrators understand patient flow, wait times, satisfaction levels, and referral patterns.

By analyzing trends in visit volume, wait times by different groups, and patient satisfaction scores across demographics (age, race, gender), the dashboard aims to identify potential bottlenecks, areas for service improvement, and insights for better resource allocation within the ER, ultimately contributing to enhanced patient care and operational efficiency.

## Steps followed

-   **Step 1 : Load Data:** Loaded data into Power BI Desktop from the provided Excel file containing ER visit records.
-   **Step 2 : Data Exploration (Power Query):** Opened Power Query Editor. Used view tab options ("column distribution", "column quality", "column profile") to understand data characteristics.
-   **Step 3 : Data Profiling Scope:** Ensured column profiling was based on the entire dataset.
-   **Step 4 : Data Cleaning:** Checked and adjusted data types (e.g., Date/Time, Numeric, Text). Handled any potential inconsistencies or missing values.
-   **Step 5 : Data Transformation (Power Query):**
    *   Created a `Morn/Eve` column based on the visit time in the `date` column to indicate AM/PM.
    *   Created a `Patient full name` column by merging relevant patient name columns/initials.
-   **Step 6 : Theme Selection:** Selected a theme for the report visuals in the View tab.
-   **Step 7 : Add Calculated Columns (DAX):**
    *   Created `Age buckets` column (e.g., 0-10, 11-20, etc.) based on the `patient_age`.
    *   Created broader `Age Group` column (e.g., Adult, Teenager, etc.) using DAX expressions based on `patient_age`.
-   **Step 8 : Create Measures (DAX):** Developed various DAX measures to calculate key metrics like Total Visits, Average Satisfaction Score, Average Wait Time, % Walk-in Patients, % Referred Patients, % Administrative Visits, etc.
-   **Step 9 : Create Dashboard Visuals:**
    *   Added KPI Cards for key metrics: Total Patient Visits, Avg Satisfaction, Service Not Rated %, Avg Wait Time (mins), Walk-in Patients %, Referred Patients %.
    *   Added a Card showing the split between Administrative and Non-Administrative appointments.
    *   Added a Bar Chart showing `Total Patients by Age Group`.
    *   Added a Column Chart showing `Patients by WeekType` (Weekday/Weekend).
    *   Added a Histogram showing `Patients Wait time(mins) Distribution`.
    *   Added a Bar Chart showing `Total Patients by department_referral`.
    *   Added an Area Chart showing `Total Patients Visit` trend by Month.
    *   Added a Donut Chart showing `Gender Breakdown`.
    *   Added a Heatmap visual showing `Avg Satisfaction Score` distribution across `patient_race` and `Age buckets`.
-   **Step 10 : Add Interactivity:** Included an AM/PM toggle/slicer to filter data based on the time of day. Added a dropdown slicer for the heatmap to select satisfaction scores.
-   **Step 11 : Add Titles:** Added text boxes for titles like "EMERGENCY ROOM VISITS OVERVIEW".


# Report Snapshot (Power BI Desktop)

![Image](https://github.com/user-attachments/assets/0e98ee19-d0cd-4f82-93fb-56f0a75f6a7a)


# Insights

The dashboard provides several key insights into ER operations:

### [1] Overall ER Metrics
-   Total Patient Visits: **9,216**
-   Average Patient Satisfaction Score: **5.47**
-   Average Patient Wait Time: **35.26 minutes**
-   Visit Type: **58.59% Walk-in** vs. 41.41% Referred Patients.
-   Admin Flag: Visits split almost evenly between Administrative (50.04%) and Non-Administrative (49.96%).
-   *Note: A high percentage (75.10%) is shown as "Service Not Rated", which may warrant investigation into data collection or calculation.*

### [2] Patient Demographics & Visit Patterns
-   **Age Group:** The majority of patients are 'Adults' (7,106), followed by 'Teenagers' (897).
-   **Gender:** Slightly more Male patients (51.1%) than Female (48.7%).
-   **Monthly Trend:** Visits peak mid-year (around July) and are lower at the beginning/end of the year.
-   **Weekly Trend:** More visits occur on Weekdays compared to Weekends.

### [3] Department Referrals
-   The most common referral destination is 'General Practice' (1,840 visits), followed by 'Orthopedics' (995). A large number (5,400) had 'None' listed as the referral department.

### [4] Wait Time & Satisfaction Insights
-   **Wait Time Distribution:** Patient wait times are distributed across various bins, with notable counts in the 20-35 minute ranges, but also extending to 45+ minutes.
-   **Satisfaction Heatmap:** This visual allows exploration of average satisfaction scores across different races and age buckets, helping to identify any demographic groups with significantly higher or lower satisfaction levels.

These insights can help hospital administration identify peak times, understand patient demographics, analyze referral patterns, monitor wait times, and pinpoint potential disparities in patient satisfaction across different groups.
