# Model Card: Student Dropout Prediction Model

## Model details
- **Name / version:** Student Dropout Prediction Model v0.1
- **Owner / contact:** Margorie Fernanda Pérez Simba
- **Date:** 2026-10
- **Architecture:** Random Forest classifier trained on structured academic, administrative, contextual, and temporal institutional data
- **License:** Internal research use only; not publicly released

## Intended use
- **Primary intended uses:** Support the early identification of students who may be at risk of dropout and help authorized institutional teams prioritize timely retention support.
- **Out-of-scope / misuse:** The model must not be used to make automatic decisions about admission, financial aid, academic sanctions, or student exclusion. It must not replace professional judgment or be applied to other institutions without external validation.
- **Intended users:** Authorized staff responsible for student retention, academic advising, institutional analytics, and academic decision support.

## Factors
- **Relevant groups / conditions:** Model performance may vary across academic colleges, degree programs, admission cohorts, study stages, and student groups with different academic or financial conditions. Changes of degree program within the same institution are excluded from the dropout outcome.
- **Evaluation factors:** Performance should be reported for the complete institutional population and disaggregated by academic college, degree program, admission cohort, and other relevant subgroups when the available sample size permits a reliable evaluation.

## Metrics
- **Performance measures:** ROC-AUC, precision-recall AUC, recall, precision, F1-score, balanced accuracy, confusion matrix, and probability calibration. Recall for the dropout class is especially important because false negatives represent students at risk who may not receive timely support.
- **Decision thresholds:** The initial classification threshold is 0.50. The final threshold should be selected using validation data and adjusted according to the institution's intervention capacity and the relative consequences of false negatives and false positives.
- **Variation approach:** Performance should be reported as the mean and standard deviation across at least five random seeds or repeated stratified validation runs, together with 95% confidence intervals when applicable.

## Evaluation data
- **Datasets:** A held-out subset of historical institutional student records that is not used for model training or hyperparameter tuning. Final evaluation should also include a later academic cohort to assess temporal generalizability.
- **Preprocessing:** Student identifiers are excluded. Missing-value treatment, categorical encoding, feature selection, scaling when required, and any class-balancing procedure must be fitted using training data only and then applied to the evaluation data. Only information available before the defined prediction point may be used to prevent data leakage.

## Training data
- **Datasets:** Historical student records from one higher education institution in Ecuador. The current model uses structured academic, administrative, contextual, and temporal variables available in institutional information systems.
- **Outcome definition:** Dropout is determined from institutional registration records according to the four regular academic periods following the student's first registration. A student who changes degree program but remains registered at the same institution is not classified as a dropout.
- **Known limitations:** The data come from a single institution and may reflect its specific academic policies, student population, data quality, and historical practices. Some relevant personal or contextual circumstances may not be recorded. Class imbalance and changes across academic periods may also affect model performance.

## Quantitative analyses
- **Overall results:** UNKNOWN: final performance results must be inserted after completing the definitive validation procedure. Results will include ROC-AUC, precision-recall AUC, recall, precision, F1-score, balanced accuracy, calibration, and the confusion matrix.
- **Disaggregated results:** UNKNOWN: subgroup evaluation is pending. Performance will be disaggregated by academic college, degree program, admission cohort, and other relevant groups with sufficient sample sizes.
- **Model interpretation:** The current prototype provides global feature importance estimates. SHAP analyses are planned to examine global predictor contributions and provide local explanations for individual predictions.

## Ethical considerations
- **Risks:** The model processes confidential student information and may reproduce historical inequalities present in institutional data. Incorrect predictions could stigmatize students, create unnecessary interventions, or fail to identify students who need support. Users may also place excessive confidence in predicted probabilities.
- **Mitigations:** Use de-identified or pseudonymized data, restrict access to authorized personnel, apply institutional data-protection procedures, evaluate performance and fairness across relevant subgroups, provide explanations for predictions, maintain human oversight, and prohibit punitive or fully automated decisions based on model outputs.

## Caveats and recommendations
- **Caveats:** The model is based on historical data from one institution and does not establish causal relationships. A high predicted probability does not mean that a student will necessarily drop out. The current version relies mainly on structured data and may not capture personal circumstances or changes in institutional conditions. Performance may decrease over time because of data drift.
- **Recommendations:** Use the model only as decision support for preventive student services. Conduct temporal and external validation, evaluate fairness across subgroups, calibrate predicted probabilities, monitor data and performance drift, document model updates, and maintain human review. Textual data, stronger temporal modeling, and explainability methods should be incorporated and evaluated before implementing the complete doctoral framework.
