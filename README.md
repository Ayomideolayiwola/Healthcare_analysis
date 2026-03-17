## 📌 Problem Statement

Healthcare organizations generate massive volumes of patient and operational data daily, yet many struggle to extract actionable insights from it. Without a clear view of key performance indicators — such as admission trends, patient demographics, diagnosis distributions, and length of stay — hospital administrators and healthcare analysts cannot make informed, data-driven decisions.

This project addresses the challenge of transforming raw, unstructured healthcare data into a clean, reliable, and visually accessible analytical resource. The goal is to build a dashboard that enables stakeholders to:

- Monitor patient admission and discharge patterns over time
- Understand the distribution of diagnoses and treatment categories
- Track hospital performance KPIs (bed occupancy, average length of stay, readmission rates, etc.)
- Identify at-risk patient segments based on demographics and medical history
- Support strategic decisions around resource allocation and care improvement

## 🧹 Data Quality Process

- Loaded the raw dataset and examined its shape, column names, and data types
- Documented all anomalies found before any transformation was applied
- For numerical fields (e.g., age, length of stay): imputed with **median** values to avoid skew from outliers
- For categorical fields (e.g., diagnosis category, gender): imputed with **mode** or labeled as `"Unknown"` where appropriate
- Removed fully duplicated rows (identical across all fields)
- Flagged and reviewed partial duplicates (same patient, different records) to determine whether they represented legitimate repeat visits or data entry errors
- Converted all date fields (admission date, discharge date, date of birth) to a consistent `YYYY-MM-DD` datetime format
- Standardized inconsistent entries — e.g., `"F"`, `"female"`, `"FEMALE"` → `"Female"`
- Created *Age Groups* (e.g., 0–18, 19–35, 36–55, 56–70, 70+) for demographic segmentation
- Re-ran all profiling checks on the cleaned dataset to confirm no residual issues
- Cross-validated row counts and key aggregates against the original dataset
- Exported the final clean dataset to CSV for use in Tableau


Key Insights

- Osteoarthritis dominates the diagnosis volume at 23,753 cases — significantly ahead of the next most common diagnosis, suggesting a strong orthopedic patient population
- Most patients (14,592) are discharged home with home health services, indicating a high proportion of patients requiring continued post-acute care
- The majority of patients (50.43%) fall under Moderate severity of illness, with only 4.70% classified as Major and 0.30% as Extreme — suggesting most admissions are manageable but not trivial
- 85.06% of patients carry a Minor risk of mortality, though the 12.64% Moderate-risk cohort (3,360 patients) warrants close monitoring
- Average length of stay is 2.7 days, with variation across age groups — older cohorts (50–69, 70+) show notably longer stays
- Hospital distribution is heavily concentrated on the East Coast, with significant gaps in the Midwest and West pointing to potential access disparities
- The healthcare system tracked 638 licensed doctors and 782 licensed nurses — a nurse-to-doctor ratio worth monitoring for staffing adequacy
  
🛠️ Tools Used
Tableau Desktop/Public: For data visualization and dashboard orchestration.
Data Cleaning: ( Excel).


---
Explore this dashboard
(https://public.tableau.com/app/profile/ayomide.olayiwola3446/viz/HealthcareAnalysis_17446237476850/KPIandPatientOverview)

---

