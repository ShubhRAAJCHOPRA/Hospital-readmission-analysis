# Hospital-readmission-analysis
Excel &amp; Power Query analysis of factors associated with 30-day hospital readmissions.
# Hospital Readmission Analysis: Identifying Factors Associated with 30-Day Readmissions

## Project Overview

This project analyzes hospital encounter data to identify factors associated with 30-day hospital readmissions.

The analysis focuses on understanding whether patient utilization history, diagnosis burden, length of stay, medication intensity, diabetes treatment, and patient demographics are associated with a higher likelihood of readmission.

The project was developed using **Microsoft Excel and Power Query**, with the analysis presented through an interactive dashboard.

---

## Business Problem

Hospital readmissions within 30 days can increase healthcare costs and place additional pressure on hospital resources.

The objective of this analysis is to answer:

> **What factors are most strongly associated with 30-day hospital readmissions?**

The analysis focuses particularly on prior hospital utilization, diagnosis burden, length of stay, medication intensity, and treatment-related factors.

---

## Dataset

The dataset contains hospital encounter-level information including:

- Patient demographics
- Hospital utilization history
- Length of stay
- Laboratory procedures
- Procedures performed
- Medication counts
- Diagnosis information
- Diabetes medication information
- Medical specialty
- 30-day readmission status

### Dataset Size

After data cleaning and removal of exact duplicate encounters:

- **48,911 hospital encounters**
- **22,609 readmissions within 30 days**
- **46.22% overall 30-day readmission rate**

---

## Tools Used

- Microsoft Excel
- Power Query
- PivotTables
- PivotCharts
- Excel Dashboard
- Data Cleaning & Transformation

---

## Data Preparation

The raw dataset was imported into Power Query and cleaned before analysis.

Key cleaning steps included:

1. Removed exact duplicate records
2. Replaced `?` values with nulls where appropriate
3. Standardized data types
4. Validated encounter IDs
5. Preserved patient IDs because patients can have multiple encounters
6. Created analytical grouping variables

### Derived Variables

The following variables were created:

- Age Group
- Length of Stay Group
- Diagnosis Burden Group
- Emergency Visit Group
- Inpatient Visit Group
- Outpatient Visit Group
- Total Prior Visits
- Prior Utilization Group
- Medication Intensity Group
- Lab Procedure Group
- Readmission Status

---

## Key Findings

### 1. Prior Hospital Utilization Is the Strongest Signal

Patients with no prior utilization had a **36.17%** readmission rate.

Patients with **6+ prior visits** had a **76.95%** readmission rate.

This represents a:

**40.78 percentage-point difference**

This was the strongest observed difference among the factors analyzed.

---

### 2. Prior Inpatient Visits Are Strongly Associated with Readmission

Readmission increased from:

- **38.52%** for patients with 0 prior inpatient visits
- **54.96%** for patients with 1 prior visit
- **65.25%** for patients with 2 prior visits
- **75.12%** for patients with 3+ prior visits

This suggests that patients with repeated previous hospitalizations represent an important high-risk population.

---

### 3. Diagnosis Burden Is Associated with Higher Readmission

Readmission increased as the number of recorded diagnoses increased:

| Diagnosis Burden | Readmission Rate |
|---|---:|
| 1–3 | 32.94% |
| 4–6 | 39.35% |
| 7+ | 49.63% |

Patients with 7+ diagnoses had a substantially higher readmission rate than patients with 1–3 diagnoses.

---

### 4. Length of Stay Shows a Gradual Increase

| Length of Stay | Readmission Rate |
|---|---:|
| 1–2 Days | 42.20% |
| 3–4 Days | 46.17% |
| 5–7 Days | 49.06% |
| 8+ Days | 50.21% |

Longer hospital stays are associated with higher readmission rates.

---

### 5. Medication Intensity Is Positively Associated with Readmission

| Medication Intensity | Readmission Rate |
|---|---:|
| 1–9 | 38.79% |
| 10–14 | 45.44% |
| 15–19 | 49.51% |
| 20+ | 49.60% |

Patients receiving higher numbers of medications showed higher readmission rates.

---

### 6. Diabetes Treatment Shows a Smaller Difference

Patients receiving diabetes medication had a readmission rate of:

**47.94%**

compared with:

**40.50%**

for patients without diabetes medication.

The difference is smaller than the effect observed for prior hospital utilization.

---

## Dashboard

The dashboard summarizes the main findings from the analysis.

![Hospital Readmission Dashboard](dashboard/Hospital_Readmission_Dashboard.png)

---

## Key Business Insight

The analysis suggests that **previous hospital utilization is the strongest observed indicator of 30-day readmission risk**.

Patients with repeated emergency or inpatient visits appear to represent a particularly high-risk population.

This suggests that hospitals could potentially use prior utilization history as one component of a risk-stratification or post-discharge follow-up framework.

---

## Recommendations

Based on the analysis:

1. **Prioritize high-utilization patients for post-discharge follow-up**
2. Identify patients with repeated emergency or inpatient visits before discharge
3. Consider diagnosis burden when assessing readmission risk
4. Review patients with longer hospital stays for additional discharge support
5. Consider medication intensity as an additional risk indicator
6. Develop targeted follow-up programs for patients with multiple previous encounters

---

## Limitations

The analysis identifies **associations rather than causation**.

For example, higher medication counts may reflect greater patient complexity rather than directly causing readmission.

Other limitations include:

- Weight data contains substantial missing values
- Some medical specialty categories have relatively small sample sizes
- Diagnosis count is used as a proxy for diagnosis burden and is not a validated clinical comorbidity index
- The analysis does not establish causal relationships
- Additional clinical and socioeconomic variables would be required for a more comprehensive risk model

---

## Project Structure

```text
hospital-readmission-analysis/
│
├── README.md
├── analysis/
│   └── Hospital_Readmission_Analysis.xlsx
├── dashboard/
│   └── Hospital_Readmission_Dashboard.png
└── documentation/
    └── Case_Study.pdf
