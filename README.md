# Customer Churn · Classification & Evaluation

An educational churn-modeling exercise using **300 synthetic e-commerce customer records**. The notebook demonstrates data preparation, class imbalance, classification, and cumulative lift analysis.

## Workflow

- Generate a synthetic binary churn label and customer features.
- Impute tenure, cap distance outliers, and encode categorical variables.
- Inspect churn balance, correlations, and tenure distributions.
- Use a 70/30 stratified split with seed 42.
- Compare logistic regression with a random forest (150 trees, maximum depth 6).
- Report recall, F1, confusion matrices, and a cumulative lift curve.

## What the saved results show

| Model | Churn recall | Churn F1 |
| --- | ---: | ---: |
| Logistic regression | 0.00 | 0.00 |
| Random forest | 0.00 | 0.00 |

Both models miss all 16 churn cases in the saved test split. This result is important: the synthetic target is generated independently of the features, so the dataset does not encode an underlying churn relationship for a model to learn.

## Scope and limitations

This demonstrates a modeling workflow, not an effective retention predictor. Statements about complaints, tenure, or order delays as churn drivers are hypotheses rather than findings established by this simulation. Median imputation currently happens before the train/test split; a stronger experiment would fit preprocessing on training data only, add a dummy baseline, and evaluate on a suitable real dataset or explicitly documented simulation. Retention recommendations have not been tested.

## Open the project

- [Analysis notebook](part2.ipynb)
- [Presentation](Part2_Churn.pptx)

## Run locally

Use Python 3 in an isolated environment:

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter lab
```

Open the notebook and run all cells from top to bottom. Data is generated inside the notebook; no external dataset download is required.

Dependencies are listed without exact version pins; results may vary slightly across library versions.
