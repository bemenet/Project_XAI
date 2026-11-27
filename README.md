# Project XAI — Explainable Human Activity Recognition (UCI HAR)

Explainable AI analysis for Human Activity Recognition (HAR) on the UCI HAR dataset (`10,299` training/full windows, `2,947` test windows, `30` subjects, `6` activities: `LAYING`, `SITTING`, `STANDING`, `WALKING`, `WALKING_DOWNSTAIRS`, `WALKING_UPSTAIRS`).

## Models & Feature Sets
- **Logistic Regression** across feature sets (`45` features: `83.92%`, `72` custom features: `90.06%`, and `561` full features: `95.45%`)
- **HAR1DCNN** trained on raw `9 × 128` windows (`90.67%` accuracy, `0.9052` macro F1)

## Key Takeaways
- **Rhythmic & posture separation:** FFT spectral/centroid features reduce walking stair confusions, while `LAYING` is largely isolated (`535/537` windows). Stationary `SITTING` and `STANDING` show higher confusion under opposing `body_gyro_x` weights and variance.
- **Counterfactual plausibility:** Searching `[-10, +10]` SD across misclassified `SITTING` windows flips predictions in some cases, but can violate physical domain constraints (such as non-negativity of `std`).
- **Scope limits:** Statistical weights, gradients, and single-feature perturbations do not establish causal biomechanics or physically realizable interventions in isolation.

## Repository Contents
- `project.ipynb` — Modeling, evaluation, and explainability notebook
- `XAI_Project_Report-1.pdf` — Project report
