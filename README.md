# Cancer Type Prediction Using High-Dimensional Genomic Data

This repository contains code and resources for a hackathon focused on building robust classification models for cancer type prediction using high-dimensional genomic data. The primary language used is Jupyter Notebook, facilitating interactive analysis and experimentation.

---

## Dataset Description

- **Total Samples:** 801 patients
- **Training Samples:** 400 (150 labeled, 250 unlabeled)
- **Test Samples:** 401 (to be predicted)
- **Features:** 14,572 gene expression measurements (real-valued)
- **Classes:** 5 cancer types (labels: 0, 1, 2, 3, 4)

### Provided Files

| File                  | Description                                                                 |
|-----------------------|-----------------------------------------------------------------------------|
| `train.csv`           | 400 samples (Id + 14,572 gene features + Class). Only 150 have Class labels.|
| `train_labels.csv`    | 150 labeled training samples (Id + Class).                                  |
| `test.csv`            | 401 test samples (Id + 14,572 gene features; no Class labels).              |
| `sample_submission.csv`| Sample submission format.                                                   |

**Columns:**
- `Id`: Unique sample identifier (`sample_XXX`)
- `gene_1, gene_2, ... gene_14572`: RNA-Seq expression levels (floats)
- `Class`: Cancer type label (0–4), only present for labeled samples

---

## Evaluation and Scoring

- **Metric:** [Macro F1-Score](https://en.wikipedia.org/wiki/F1_score#Definition)
  - Each class’s F1-score is computed independently; Macro F1 is their average.
  - Suitable for imbalanced, multi-class settings typical in medical datasets.

**Formula:**
- For each class \( i \):

  \[
  \text{F1}_i = \frac{2 \times \text{Precision}_i \times \text{Recall}_i}{\text{Precision}_i + \text{Recall}_i}
  \]
- Macro F1-Score:

  \[
  \text{Macro F1} = \frac{1}{k} \sum_{i=1}^{k} \text{F1}_i
  \]
  where \( k = 5 \) (number of classes).

---

## Submission Guidelines

- **Format:** CSV file with columns: `Id,Class`
- **Example:**
  ```
  Id,Class
  sample_0,0
  sample_1,1
  sample_2,4
  

## Getting Started

1. **Download the Data:** Get all four CSV files from the competition's data tab.
2. **Explore the Starter Notebook:** Review data structure, exploratory analysis, and sample submission code.
3. **Read Evaluation Criteria:** Understand how Macro F1-Score is calculated and used.
4. **Review the Rules:** Pay attention to leaderboard, collaboration, and submission limitations.
5. **Build Incrementally:** Start with simple baselines, then iterate and refine your models.

---

## Project Structure

```

│   ├── train.csv
│   ├── train_labels.csv
│   ├── test.csv
|   |--- 20251918_Chandrakant.ipynb
│   └── sample_submission.csv
│   └── starter_notebook.ipynb
└── README.md
```


---

## Resources and Guidelines

- [Kaggle Competition Documentation](https://www.kaggle.com/docs/competitions) – Info on participation, data handling, and submissions.
- Starter notebook provides data loading, EDA, and submission file creation.
- **Leaderboard:** Public and private scores are based on Macro F1-Score.
- **Notebook Submission:** Required for methodology, not just leaderboard performance.

**Assessment Criteria:**
- Code Quality: Clean, well-documented, and reproducible code
- Methodology: Sound ML practices and experimental design
- Innovation: Creative solutions for data/scenario challenges
- Analysis: Insightful discussion of results and model behavior
- Documentation: Clear explanations and rationale

---

## Requirements

- Python 3.x
- Jupyter Notebook or JupyterLab
- Key libraries: `numpy`, `pandas`, `scikit-learn`, `matplotlib`, `seaborn`, etc.
- Install dependencies:
  ```bash
  pip install -r requirements.txt
  ```

---

## Contributions

Contributions are welcome! Please open an issue or submit a pull request for improvements, bug fixes, or new analysis notebooks.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

**Author:** [chandrakant1212](https://github.com/chandrakant1212)
