
# DAX Formulas & Data Transformations

This document provides an overview of all key DAX measures and data transformations used in the Power BI dashboard analyzing hospital readmissions of diabetes patients.

---

## Data Preprocessing

- **Binary readmission column**:  
  A new column `readmitted_binary` was created to simplify readmission status:
  - If `readmitted` was either `<30` or `>30` → `1` (Readmitted)
  - If `readmitted` was `NO` → `0` (Not readmitted)

- **Data cleaning**:
  - Unimportant columns and those with excessive missing values were removed.
  - Remaining missing values were standardized as `null`.

- **Gender filtering**:
  - Only entries labeled `Male` and `Female` were retained. Other values were excluded due to low representation.

---

## Key Measures

### Percent_Readmitted
Percentage of patients who were readmitted:
```DAX
Percent_Readmitted = 
    SUM('diabetic_data'[readmitted_binary]) 
    / COUNTROWS('diabetic_data')
```

---

### ReadmissionRate
Alternative way to calculate readmission rate using `encounter_id`:
```DAX
ReadmissionRate = 
    DIVIDE(
        SUM('diabetic_data'[readmitted_binary]),
        COUNT('diabetic_data'[encounter_id])
    )
```

---

### ReadmissionByInsulin
Proportion of readmissions relative to insulin usage:
```DAX
ReadmissionByInsulin = 
    DIVIDE(
        COUNTROWS('diabetic_data'), 
        CALCULATE(
            COUNTROWS('diabetic_data'), 
            ALLEXCEPT('diabetic_data', 'diabetic_data'[insulin])
        )
    )
```

---

### ReadmissionRateByStay
Readmission rate per length of hospital stay:
```DAX
ReadmissionRateByStay = 
    DIVIDE(
        COUNTROWS(
            FILTER('diabetic_data', 'diabetic_data'[readmitted_binary] = 1)
        ),
        CALCULATE(
            COUNTROWS('diabetic_data'), 
            ALLEXCEPT('diabetic_data', 'diabetic_data'[time_in_hospital])
        )
    )
```

---

### ReadmissionRateByStayAndInsulin
Readmission rate based on both length of stay and insulin regimen:
```DAX
ReadmissionRateByStayAndInsulin = 
    DIVIDE(
        CALCULATE(
            COUNTROWS('diabetic_data'),
            'diabetic_data'[readmitted_binary] = 1
        ),
        CALCULATE(
            COUNTROWS('diabetic_data'),
            ALLEXCEPT('diabetic_data', 'diabetic_data'[time_in_hospital], 'diabetic_data'[insulin])
        )
    )
```

---

##  Sorting Transformation

### Age_Sort_Order
Created to sort age categories correctly in visuals:
```DAX
Age_Sort_Order = 
    SWITCH('diabetic_data'[age],
        "[0-10]", 1,
        "[10-20]", 2,
        "[20-30]", 3,
        "[30-40]", 4,
        "[40-50]", 5,
        "[50-60]", 6,
        "[60-70]", 7,
        "[70-80]", 8,
        "[80-90]", 9,
        "[90-100]", 10
    )
```

---

## Notes

- All measures are based on cleaned and filtered data.
- Measures are designed for use with Power BI visuals including KPIs, bar charts, and heatmaps.
- Clinical interpretations are provided in the [README](./README.md) file.
