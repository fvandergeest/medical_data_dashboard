# Hospital Readmissions of Diabetes Patients - Power BI Dashboard

## Summary
In this project, I analyzed hospital admissions of diabetes patients using a publicly available dataset. The main goal was to identify factors that contribute to hospital readmissions and to explore how these factors interact with one another. With my background in Technical Medicine, I focused not only on data analysis, but also on interpreting the results from a clinical perspective, aiming to extract insights that are meaningful in real-world healthcare settings.

---

## Dashboard Overview

![Image](https://github.com/user-attachments/assets/97a28078-1115-45c1-8682-f9857742e689)

---

## Project Goal

This dashboard aims to:

- Visualize how key patient- and treatment-related factors may influence hospital readmission.
- Reveal patterns within patient subgroups (e.g., by age, sex, length of stay, and insulin treatment).
- Generate clinically meaningful insights to support patient care, risk stratification, and early identification of high-risk patients.

Early readmission of patients with diabetes is clinically significant, as it is associated with increased morbidity, mortality and healthcare costs. By analysing real-world hospital data, this project can provide greater insight into the factors that play a role in readmission and help identify opportunities to improve diabetes management and reduce avoidable readmissions.(1)

---


##  Tools & Skills Used

- **Power BI**: For interactive data visualizations
- **DAX**: Custom measures for readmission rates, length of stay, etc.  
- **Clinical Analysis**: Medical interpretation of patterns, including bias and confounding factors

---

## Project Structure

- `dashboard.pbix` – Power BI file  
- `README.md` – Documentation  
- `dax_formulas.md` – Overview of custom DAX measures  

---

## Dataset Overview

- **Source**: [UCI Diabetes Readmission Dataset](https://archive.ics.uci.edu/ml/datasets/diabetes+130-us+hospitals+for+years+1999-2008) (1)  
- **Patients**: ~71,500  
- **Variables**: 50+  
- **Time period**: Data collected between 1999 and 2008 from 130+ hospitals in the U.S.  
- **Key columns**:
  - `readmitted`: Indicates if the patient was readmitted within or after 30 days.
  - `age`, `gender`: Demographic details.
  - `num_medications`, `time_in_hospital`: Healthcare utilization.
  - `insulin`, `medications` : Clinical variables.
  - `diag_1`, `diag_2`, `diag_3` : ICD 9 codes and diagnoses

---

## Dashboard Visuals & Insights

### 1. **KPI Cards**
- **Total patients**: 71,520  
- **Readmission rate**: 46.1%  
- **Avg. hospital stay**: 4.4 days  
- **Avg. number of medications**: 16 per patient

![Image](https://github.com/user-attachments/assets/e5fc3bbc-9bc5-4740-81e2-de41b9a563c8)

### 2. **Total Readmissions by Age and Gender**
- **What it shows**: Total number of readmissions split by age group and gender.
- **Clinical relevance**: Older patients are generally more prone to readmissions(2).
- **Observation**: Highest readmissions in the 60–80 age group; minimal difference between males and females.

![Image](https://github.com/user-attachments/assets/dbc2c095-9085-4764-bf67-5fd0b574f9c6)

### 3. **Readmission Rates by Insulin Use and Readmission Timing**
- **What it shows**: The timing of readmission rate (<30, >30 days or no readmission) by insulin usage category (No, Steady, Up, Down).
- **Clinical relevance**: Insulin management is central to diabetes care. Patterns here may reflect the effectiveness or stability of glycemic control during hospitalization.
- **Observation**: Patients with ‘Up’ or ‘Down’ insulin adjustments had more readmissions, which may indicate treatment instability.

![Image](https://github.com/user-attachments/assets/0e90e945-2c7b-4478-b83e-4b3fee8316ac)

### 4. **Readmission Rate vs. Length of Stay**
- **What it shows**: Readmission percentage across different hospital stay durations.
- **Clinical relevance**: Length of stay can reflect patient severity or premature discharge. This metric helps assess whether certain durations are associated with higher readmission risk.
- **Observation**: A moderate increase in readmission rate is observed with longer stays, especially beyond 8 days, potentially indicating more complex or unstable cases.

![Image](https://github.com/user-attachments/assets/f4d8c56f-6c5c-4871-9409-61c9b264759f)

### 5. **Heatmap: Interaction Between Length of Stay and Insulin changes**
- **What it shows**: A combined view of how readmission rate varies across both insulin treatment types and hospital stay durations.
- **Clinical relevance**: Displays interaction between two key variables. It can help to identify high-risk combinations that can be used for risk prediction models or guide discharge protocols.
- **Observation**: Patients with longer stays and insulin titration (“Up” or “Down”) showed the highest readmission rates, indicating a potential need for more intensive post-discharge support in this group.

![Image](https://github.com/user-attachments/assets/e0006a3c-6f6c-49fd-a33b-fbdcdfda4f02)

---

## Clinically Applicable Insights

- Patients with unstable insulin regimens (adjustments up or down) may benefit from closer monitoring at discharge.  
- Older patients (60–80) and those with longer hospital stays show a higher readmission risk.  
- Unstable insulin regimens  and length of stay may contribute to risk profiles.  
- Combinations of age, insulin type, and hospitalization duration could potentially inform predictive models.

---

## Dataset source
The dataset that was used is from the UC Irvine Machine learning repository. The data was anonymised and approved for any use.(1)

---
## References
1. Clore, J., Cios, K., DeShazo, J., & Strack, B. (2014). Diabetes 130-US Hospitals for Years 1999-2008 [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5230J.
2. Robbins, T. D., Keung, S. L. C., Sankar, S., Randeva, H., & Arvanitis, T. N. (2019). Risk factors for readmission of inpatients with diabetes: a systematic review. Journal of Diabetes and its Complications, 33(5), 398-405.

