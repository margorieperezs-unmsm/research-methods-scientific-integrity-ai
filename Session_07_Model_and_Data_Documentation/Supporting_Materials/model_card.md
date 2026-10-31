# Model Card: Proposed Student Dropout Prediction Framework

## Model details
- **Name / version:** Explainable, Multimodal, and Temporal Student Dropout Prediction Framework v0.1 (proposed)
- **Owner / contact:** Margorie Fernanda Pérez Simba
- **Date:** 2026-10
- **Development status:** Research design stage. The definitive model has not yet been trained or validated, and no operational version has been deployed.
- **Architecture:** Proposed explainable, multimodal, and temporal AI framework combining structured institutional variables, temporal patterns, and authorized textual information. Candidate algorithms and component designs will be compared during the doctoral study rather than assumed in advance.
- **License:** Research documentation only. The proposed model has not been publicly released.

## Intended use
- **Primary intended uses:** If adequately validated, support the early identification of students who may be at risk of dropout and help authorized institutional teams prioritize timely, preventive retention support.
- **Out-of-scope / misuse:** The model must not be used to make automatic decisions about admission, financial aid, academic sanctions, or student exclusion. It must not replace professional judgment or be applied to other institutions without external validation.
- **Intended users:** Authorized staff responsible for student retention, academic advising, institutional analytics, and academic decision support.

## Factors
- **Relevant groups / conditions:** Model performance may vary across academic colleges, degree programs, admission cohorts, study stages, and student groups with different academic or financial conditions. Changes of degree program within the same institution are excluded from the dropout outcome.
- **Evaluation factors:** Performance should be reported for the complete institutional population and disaggregated by academic college, degree program, admission cohort, and other relevant subgroups when the available sample size permits a reliable evaluation.

## Metrics
- **Performance measures:** ROC-AUC, precision-recall AUC, recall, precision, F1-score, balanced accuracy, confusion matrix, and probability calibration. Recall for the dropout class is especially important because false negatives represent students at risk who may not receive timely support.
- **Decision thresholds:** No operational threshold has been selected. Candidate thresholds will be evaluated using validation data and aligned with the institution's intervention capacity and the relative consequences of false negatives and false positives.
- **Variation approach:** Performance will be reported across multiple predefined random seeds or repeated validation runs using the mean, standard deviation, and 95% confidence intervals when applicable. Temporal variation across cohorts will also be examined.

## Evaluation data
- **Datasets:** The definitive evaluation dataset has not yet been constructed. The planned design will reserve data that are not used for model training or hyperparameter tuning and will include later academic cohorts for temporal validation when the available outcome window permits.
- **Preprocessing:** The planned pipeline will remove or pseudonymize direct identifiers. Missing-value treatment, categorical encoding, feature selection, scaling when required, and any class-balancing procedure will be fitted using training data only and then applied to validation and test data. Only information available before the defined prediction point will be used to prevent data leakage.

## Training data
- **Datasets:** A confidential preliminary extract of real historical student records from one higher education institution in Ecuador is available to assess data availability and inform the research design. It is not the definitive thesis dataset and has not been used to claim final model performance. The definitive dataset will be constructed after the scope, prediction point, eligible population, authorized variables, and available cohorts are finalized.
- **Outcome definition:** Dropout is determined from institutional registration records according to the four regular academic periods following the student's first registration. A student who changes degree program but remains registered at the same institution is not classified as a dropout.
- **Known limitations:** The preliminary extract does not yet represent the final study population, predictor set, or cohort range. The definitive data will come from a single institution and may reflect its specific academic policies, student population, data quality, and historical practices. Some relevant circumstances may not be recorded, and class imbalance or changes across periods may affect performance.

## Quantitative analyses
- **Overall results:** UNKNOWN: no definitive thesis model has been trained or validated. Final results will be reported only after the dataset and validation protocol are finalized and will include ROC-AUC, precision-recall AUC, recall, precision, F1-score, balanced accuracy, calibration, and the confusion matrix.
- **Disaggregated results:** UNKNOWN: subgroup evaluation has not yet been conducted. Performance will be disaggregated by academic college, degree program, admission cohort, and other relevant groups when sample sizes permit reliable reporting.
- **Model interpretation:** UNKNOWN: no definitive model explanations are available. The planned evaluation will compare global and local explanation methods, including SHAP when appropriate, and assess whether explanations are useful to authorized institutional users.

## Ethical considerations
- **Risks:** The proposed model would process confidential student information and could reproduce historical inequalities present in institutional data. Incorrect predictions could stigmatize students, create unnecessary interventions, or fail to identify students who need support. Users might also place excessive confidence in predicted probabilities.
- **Mitigations:** Use de-identified or pseudonymized data, restrict access to authorized personnel, apply institutional data-protection procedures, evaluate performance and fairness across relevant subgroups, provide explanations for predictions, maintain human oversight, and prohibit punitive or fully automated decisions based on model outputs.

## Caveats and recommendations
- **Caveats:** This document describes a proposed system, not a completed or deployable model. Future predictions will be based on historical data from one institution and will not establish causal relationships. A high predicted probability will not mean that a student will necessarily drop out, and performance may change over time because of data drift.
- **Recommendations:** Do not deploy the system until the definitive dataset, prediction point, validation protocol, fairness assessment, calibration, explainability analysis, and governance requirements have been completed. If validated, use it only as decision support for preventive student services with human review, temporal monitoring, and documented model updates.
