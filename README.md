# Clinical Melioidosis Benchmark Dataset (50,000 Patient Cohort)

## Overview
This package contains a high-fidelity, synthetic 50,000-record clinical dataset specifically engineered to train and benchmark causal discovery and probabilistic tabular transformer models for tropical infectious disease recognition and severity discrimination.

---

## Package Directory Structure
```
.
├── melioidosis_clinical_dataset_50k.csv      # Complete 50,000 record master dataset
├── data_splits/
│   ├── train_split.csv                       # Training subset (70% - 35,000 records)
│   ├── val_split.csv                         # Validation subset (15% - 7,500 records)
│   └── test_test.csv                         # Holdout Test subset (15% - 7,500 records)
├── figures/
│   ├── fig1_causal_dag.png                   # Causal DAG pathways
│   ├── fig2_dataset_partitioning_workflow.png # Zero-leakage partitioning workflow
│   ├── fig3_attribute_correlation_heatmap.png # Multi-attribute correlation heatmap
│   ├── fig4_roc_auc_performance_curves.png   # Model ROC-AUC comparison
│   └── fig5_severity_discrimination_biomarkers.png # Biomarker severity discrimination
├── validation/
│   ├── validation_report_100pct_pass.json    # JSON automated audit report
│   └── validation_summary.txt                # Text audit summary
└── README.md                                 # Package Documentation
```

---

## Dataset Attributes (29 Columns)
1. `patient_id`: Unique identifier (MEL-XXXXXX)
2. `patient_name`: Synthetic full patient name
3. `gender`: 3-tier gender schema (`Male`, `Female`, `Non-Binary`)
4. `age`: Patient age in years (18-90)
5. `country`: Endemic geographic regions (Thailand, Australia, India, Vietnam, Malaysia, Cambodia, Laos, Singapore)
6. `rural_exposure`: Binary indicator (0/1)
7. `agricultural_work`: Binary indicator (0/1)
8. `recent_flood_exposure`: Exposure to monsoon/flood waters (0/1)
9. `diabetes_mellitus`: Underlying comorbidity (0/1)
10. `chronic_kidney_disease`: Pre-existing renal condition (0/1)
11. `chronic_lung_disease`: Pre-existing pulmonary condition (0/1)
12. `immunosuppression`: Immunocompromised status (0/1)
13. `fever_duration_days`: Duration of presenting fever
14. `cough`: Presenting respiratory symptom (0/1)
15. `chest_pain`: Presenting chest symptom (0/1)
16. `skin_lesions_abscesses`: Cutaneous manifestations (0/1)
17. `hepatosplenomegaly`: Visceral organ enlargement (0/1)
18. `neurological_signs`: Central nervous system involvement (0/1)
19. `wbc_count`: White Blood Cell count ($10^9$/L)
20. `neutrophil_percentage`: Neutrophil fraction (%)
21. `crp_level`: C-Reactive Protein (mg/L)
22. `procalcitonin`: Serum Procalcitonin (ng/mL)
23. `creatinine`: Serum Creatinine (mg/dL)
24. `blood_glucose`: Fasting/Random Blood Glucose (mg/dL)
25. `melioidosis_confirmed`: Primary target - Disease Confirmation (0/1)
26. `severity_grade`: Target - Ordinal Severity (`Non-Melioidosis`, `Localized / Mild`, `Pulmonary / Moderate`, `Disseminated / Severe`, `Septic Shock / Critical`)
27. `icu_admission`: ICU admission requirement (0/1)
28. `length_of_stay`: Hospital stay duration (days)
29. `mortality_status`: In-hospital mortality outcome (0/1)

---

## Quality Control & Validation Standard
- **Zero Data Leakage:** Stratified partition isolation guarantees zero patient overlap across training, validation, and testing sets.
- **100% Validation Verification:** Validated for zero missing values, zero duplicate keys, and realistic physiological correlations.
- **Ethical Compliance:** Synthetic dataset generated using Bayesian causal modeling; contains zero real-world Protected Health Information (PHI).


## First I caluclate blood gluclose to known that is it effect to Melioidosis
