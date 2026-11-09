# Datheon Task 1: Iris Classification

Compare Logistic Regression and a Decision Tree using the Iris dataset.

## Submission files

- `Datheon_Task1_Iris_Classification.ipynb`: the required submission notebook, with executed code, explanations, classification reports, confusion matrix heatmaps, pairplot, and decision boundary plots.
- `iris.csv`: a CSV export of the same scikit-learn Iris dataset used in the notebook.
- `requirements.txt`: the analysis packages and tested versions.
- `README.md`: project overview and instructions.

## Run the notebook

Use Python 3.11 or newer. This solution was executed using Python 3.12.
Open a terminal in this folder and run:

```bash
python -m pip install notebook -r requirements.txt
python -m notebook
```

Open `Datheon_Task1_Iris_Classification.ipynb` and run its cells from top to bottom.
The notebook loads Iris directly from scikit-learn, so it does not require a
separate data download. The CSV is included for reference.

## Method

The dataset has 150 flowers, four measurements in centimetres, and three species.
A stratified 80/20 split gives 120 training flowers and 30 test flowers;
random_state is 42. The scaler is fitted only on training data. Both main
models use all four features. The pairplot uses training rows. Separate
models using two petal measurements illustrate decision boundaries.

The notebook checks missing values and repeated rows. It retains one repeated
measurement row in the benchmark dataset; both matching rows are in training.

## Results

| Model | Accuracy | Macro precision | Macro recall | Macro F1-score |
| --- | --- | --- | --- | --- |
| Logistic Regression | 93.33% | 0.9333 | 0.9333 | 0.9333 |
| Decision Tree | 93.33% | 0.9333 | 0.9333 | 0.9333 |

Both models classify 28 of 30 test flowers correctly. Each confuses one
versicolor flower with virginica and one virginica flower with versicolor.
All 10 setosa test flowers are correctly classified. The models tie on this
split; the small test sample does not establish a better model or performance
on new real-world collections. Model settings were not tuned on the test set.

## Source

The dataset is scikit-learn's bundled Iris dataset.

- https://scikit-learn.org/1.8/datasets/toy_dataset.html#iris-plants-dataset
- https://scikit-learn.org/1.8/common_pitfalls.html#data-leakage
- https://scikit-learn.org/1.8/modules/generated/sklearn.metrics.classification_report.html
