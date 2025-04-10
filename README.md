# Hospital Readmissions of Diabetes Patients - Power BI Dashboard

## Summary
In this project, I analyzed hospital admissions of diabetes patients using a public dataset. The goal is to identify factors contributing to readmissions and explore how these factors interrelate. With my background in Technical Medicine, I focus on the clinical relevance of the findings and potential applications in healthcare.

---
## Dashboard Overview

![Image](https://github.com/user-attachments/assets/1b124242-b044-4eec-a1f4-8f136f99b423)



## Project Goal

This dashboard aims to:

- Identify variables associated with increased readmission risk.
- Reveal patterns within patient subgroups (e.g., by age, sex, insulin treatment).
- Generate clinically meaningful insights that can support patient care, risk stratification, and potentially prevent avoidable readmissions.

---


##  Tools & Skills Used

- **Power BI**: For data visualization, DAX measures, slicers, and interactivity  
- **Data Cleaning**: Performed in Power Query  
- **DAX**: Custom measures for readmission rates, age categories, etc.  
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
- **Clinical relevance**: Older patients are generally more prone to readmissions (see *Zhou et al., 2016*).
- **Observation**: Highest readmissions in the 60–80 age group; minimal difference between males and females.

![Image](https://github.com/user-attachments/assets/dbc2c095-9085-4764-bf67-5fd0b574f9c6)

### 3. **Readmission Rates by Insulin Use and Readmission Timing**
- **What it shows**: Percentage of readmissions per insulin usage type, divided by readmission timing.
- **Why rates matter**: Shows proportional differences regardless of group size.
- **Insight**: Patients with ‘Up’ or ‘Down’ insulin adjustments had more readmissions, which may indicate treatment instability.

![Image](https://github.com/user-attachments/assets/0e90e945-2c7b-4478-b83e-4b3fee8316ac)

### 4. **Readmission Rate vs. Length of Stay**
- **What it shows**: Readmission percentage across different hospital stay durations.
- **Insight**: Slightly increasing trend; longer stays may be linked to more severe conditions or complications.
- **Clinical use**: May support targeted follow-up strategies post-discharge for longer stays.

![Image](https://github.com/user-attachments/assets/f4d8c56f-6c5c-4871-9409-61c9b264759f)

### 5. **Heatmap: Interaction Between Length of Stay and Insulin changes**
- **What it shows**: Visualizes the combination of insulin treatment and hospital stay duration.
- **Strength**: Displays interaction between two key variables.
- **Clinical potential**: May guide discharge protocols or inform risk prediction models.

![Image](https://github.com/user-attachments/assets/e0006a3c-6f6c-49fd-a33b-fbdcdfda4f02)

---

## Clinically Applicable Insights

- Patients with unstable insulin regimens (adjustments up or down) may benefit from closer monitoring at discharge.  
- Older patients (60–80) and those with longer hospital stays show a higher readmission risk.  
- Medication count and length of stay may contribute to risk profiles.  
- Combinations of age, insulin type, and hospitalization duration can inform predictive models.

---

## Dataset source
The dataset that was used is from the UC Irvine Machine learning repository. The data was anonymised and approved for any use.(1)

---
## References
1. Clore, J., Cios, K., DeShazo, J., & Strack, B. (2014). Diabetes 130-US Hospitals for Years 1999-2008 [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5230J.
2. Strack et al. (2014). *Predicting 30-Day All-Cause Readmissions Using Electronic Health Record Data*. [UCI Dataset](https://archive.ics.uci.edu/ml/datasets/diabetes+130-us+hospitals+for+years+1999-2008)  
3. Zhou et al. (2016). *Risk factors for hospital readmission in patients with diabetes*. *Diabetes Research and Clinical Practice*.

