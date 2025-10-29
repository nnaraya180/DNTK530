
# Analysis of Hospital Length of Stay by Procedure Type  
**Course:** DNTK 530 — Working with Data (Fall 2025)  
**Author:** Neil Narayanan  

---

## 📌 Project Overview  
This project explores patterns in hospital Length of Stay (LOS) using a subset of the MIMIC-IV clinical database. The main objective was to determine whether differences in procedural care—such as invasive ventilation, catheter placement, or major surgery—are associated with longer or shorter hospital stays.

To accomplish this, multiple dataset tables were merged and cleaned, and both qualitative and quantitative methods were used to explore the procedural landscape, categorize interventions, and analyze their relationship to patient outcomes.

---

## 🎯 Research Goal  
**How do different types of medical procedures impact a patient's length of stay, once procedures are grouped into clinically meaningful categories?**

Early attempts focused on identifying “advanced” vs. “standard” procedures, but this proved difficult due to sparse and inconsistent naming in the data. The refined approach categorizes procedures using the ICD-10-PCS code structure, a reliable clinical standard.

---

## 🩺 Data Source  
This project uses the **MIMIC-IV Demo (v2.2)** dataset  
Kaggle link: *https://www.kaggle.com/datasets/montassarba/mimic-iv-clinical-database-demo-2-2*

Key tables used:
- `admissions.csv` — LOS, demographics, outcomes
- `patients.csv` — age, gender, mortality timing
- `procedures_icd.csv` — procedural details
- `d_icd_procedures.csv` — procedure name lookup

---

## 🛠 Methods & Workflow

### ✅ Data Merging & Cleaning
- Converted timestamps and computed **Length of Stay (days)**
- Merged admissions → patients → procedures
- Removed unused columns and handled missing procedure cases

### ✅ Exploratory Data Analysis
- Identified **352 unique procedure types**
- Found that ~68% occur **only once**
- Visualized frequency distribution and admission-level procedure counts

### ✅ Classification of Procedures  
Two grouping strategies were tested:

| Method | Outcome |
|-------|---------|
| Keyword-based matching | Too many procedures classified as “Other” |
| **ICD-10-PCS structural grouping** ✅ | Clinically meaningful and complete |

Procedures were grouped into categories such as:
- Medical-Surgical  
- Administration (Medication/Nutrition)  
- Monitoring & Measurement  
- ECMO & Cardiopulmonary Bypass  
- Diagnostic Imaging  
*(additional categories included)*

---

## 📊 Analysis & Results  
Visuals and statistical comparison of **LOS across ICD-based procedure categories** will be included here as analysis continues.  
Preliminary findings suggest:
- Admissions involving medical-surgical and life-support categories show longer LOS
- Admissions with no procedures serve as a useful baseline control group

---

## ✅ Future Extensions  
- Adjust LOS comparisons for **illness severity** (e.g., SOFA score)
- Add ICU procedure data for better coverage of critical care technologies
- Explore readmission rates linked to procedure categories

---

## 📂 Repository Structure (current)
├── designtk530I7.py
├── designtk530I8.ipynb
├── README.md
└── data/ (not included due to licensing)


---

## 📝 Ethical Note  
This project uses a de-identified dataset and adheres to MIMIC-IV data privacy and usage requirements.
EOF
