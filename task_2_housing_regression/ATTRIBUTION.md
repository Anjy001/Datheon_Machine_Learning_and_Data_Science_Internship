# Data and method references

The analysis uses the user-supplied `housing.csv`, preserved byte for byte.
SHA-256: `8a3727f4cf54ac1a327f69b1d5b4db54c5834ea81c6e4efc0d163300022a685e`.

Its 20,640 rows, columns, five ocean categories, and 207 missing bedroom
values match the modified California Housing benchmark described by
Aurélien Géron's dataset documentation. The exact download route of this
uploaded copy was not supplied; matching the documented schema is not a
claim that its download history was independently established.

The maintainer traces the benchmark to the 1990 California census and to
Pace, R. Kelley, and Ronald Barry (1997), “Sparse Spatial Autoregressions,”
Statistics & Probability Letters, 33(3), 291–297. The modified teaching
version adds ocean proximity and removes 207 bedroom entries.
The corresponding Kaggle dataset listing identifies its license as
CC0: Public Domain. No software license is being applied to third-party data.

## Dataset documentation consulted

- https://github.com/ageron/data/blob/main/housing/README.md
- https://www.kaggle.com/datasets/camnugent/california-housing-prices

## Method documentation consulted

- https://scikit-learn.org/1.8/common_pitfalls.html#data-leakage
- https://scikit-learn.org/1.8/modules/generated/sklearn.model_selection.GridSearchCV.html
- https://scikit-learn.org/1.8/modules/generated/sklearn.compose.ColumnTransformer.html
- https://scikit-learn.org/1.8/modules/linear_model.html

## Data dictionary

| Column | Meaning and unit |
| --- | --- |
| longitude, latitude | Area coordinates in degrees |
| housing_median_age | Median housing age in years; recorded maximum 52 |
| total_rooms, total_bedrooms | Area-level room and bedroom counts |
| population, households | Area-level people and household counts |
| median_income | Scaled income measure retained in its supplied dataset units |
| median_house_value | Area median house value in dollars; recorded upper limit $500,001 |
| ocean_proximity | Five broad ocean-location categories |

Task requirements were supplied as Datheon Task 2 screenshots: compare OLS,
Ridge, and Lasso, handle missing values and multicollinearity, engineer an
interaction, encode categories, scale numeric inputs, tune alphas, and report
RMSE, MAE, R², predicted-versus-actual plots, and residual plots.
