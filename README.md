# Bank Term Deposit Subscription Prediction

An Apziva machine learning project predicting whether a bank customer will subscribe to a term deposit (`y`) using pre-call marketing and customer information.

## Objective

- Predict term-deposit subscription (`yes`/`no`).
- Meet the project requirement of at least **81% mean accuracy over five-fold cross-validation**.
- Identify promising customer segments and explain the most useful predictive features.

## Method

The notebook covers exploratory data analysis, stratified train/test splitting, categorical and numerical preprocessing, optional month-cycle features, class-imbalance handling with random oversampling, model comparison, five-fold cross-validation, optional hyperparameter search, out-of-fold threshold selection, final held-out evaluation, lift analysis, permutation feature importance, and error analysis.

**Call duration is excluded** from the operational prediction features because it is unknown before a call begins. Resampling and preprocessing are fitted inside training folds to reduce leakage.

## Results reported in the notebook

- The strongest original-distribution model is **Hist Gradient Boosting**, with approximately **92.83% mean five-fold accuracy**.
- The tuned decision threshold is approximately **0.14**; the notebook reports about **91.16% held-out test accuracy** and **34.60% class-1 F1** at that threshold.
- The **top 10%** of customers by predicted subscription probability had a reported **28.25% subscription rate**, compared with an overall rate of **7.24%**.
- Predictive signals highlighted include **campaign month, contact type, and day of month**. These are predictive associations, not proof of causation.

**Important:** Overall accuracy is high partly because the dataset is imbalanced. Review class-1 precision, recall, F1, average precision, and the confusion matrix before interpreting model quality. Figures above are notebook-reported results; reproduce them by running the notebook with the original dataset and compatible dependencies.

## Repository layout

```text
ATCPCqN2T4VTrt14/
├── README.md
├── requirements.txt
├── .gitignore
├── GITHUB_UPLOAD.md
├── data/
│   └── README.md
└── notebooks/
    └── bank_subscription.ipynb
```

## Run locally

1. Install Python and Jupyter.
2. Place `term-deposit-marketing-2020.csv` in the `data/` directory.
3. From the repository root, install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Launch Jupyter and open `notebooks/bank_subscription.ipynb`:

   ```bash
   jupyter notebook
   ```

5. Run cells in order. The notebook reads `../data/term-deposit-marketing-2020.csv` relative to the `notebooks/` folder.

## Limitations

Class imbalance makes accuracy alone misleading; oversampling is limited to training folds. Segment-level associations are not causal effects. Actual performance depends on the dataset version and runtime dependencies.
