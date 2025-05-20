Wine Quality & Type Analysis and Modeling in R

A quick summary of what each column typically represents in a wine quality dataset:
    1.	type – Type of wine (red or white).
    2.	fixed.acidity – Tartaric acid content.
    3.	volatile.acidity – Acetic acid content; too much can make the wine taste vinegary.
    4.	citric.acid – Can add freshness and flavor.
    5.	residual.sugar – Sugar remaining after fermentation.
    6.	chlorides – Salt content.
    7.	free.sulfur.dioxide – Free form of SO₂; prevents microbial growth and oxidation.
    8.	total.sulfur.dioxide – Sum of free and bound forms; high values can affect taste and health.
    9.	density – Density of the wine; related to sugar and alcohol content.
    10.	pH – Acidity level.
    11.	sulphates – Wine preservative; contributes to SO₂ levels.
    12.	alcohol – Alcohol percentage by volume.
    13.	quality – Wine quality score (rated 0–9, based on sensory data).
-------------------------------------------------------------------------------
  1. Exploratory Data Analysis (EDA)
    •	Summary Statistics: Used summary() to understand distributions, central tendencies, and missing data.
    •	Class-wise Analysis: Compared red vs. white wines using grouped summaries and visualizations (ggplot2).
    •	Outlier Detection: Used boxplots and z-scores to identify extreme values for features like residual.sugar, free.sulfur.dioxide
  2. Feature Relationships
    •	Correlation Matrix: Visualized feature correlations using corrplot and ggcorrplot.
    •	Pairwise Plots: Used GGally::ggpairs() to explore multivariate relationships, colored by wine type.
  3. Modeling Tasks
----------------------------------------------------------------------------------

I. Binary Classification (Red vs. White Wine)
Goal: Predict type (red or white) using physicochemical features.
  •	Models Used:
    o	Logistic Regression
    o	Random Forest
    o	Support Vector Machine
    o	XGBoost
  •	Evaluation:
    o	Confusion matrix
    o	Area Under the Curve (AUC)
    o	Feature importance plots (especially for RF & XGBoost)
--------------------------------------------------------------------------------------

II. Regression (Predict Wine Quality Score)
Goal: Predict numeric quality (0–9)
  •	Models Used:
    o	Linear Regression
    o	Decision Tree Regression
    o	Random Forest Regression
    o	XGBoost Regression
  •	Evaluation Metrics:
    o	RMSE, MAE, R²
    o	Feature importance visualization (gain, frequency)
---------------------------------------------------------------------------------------

III. Multiclass Classification (Discrete Quality)
Goal: Predict exact quality class (0–9)
  •	Issue: Class imbalance and overlap led to poor performance.
  •	Models Used:
    o	Multinomial Logistic Regression
    o	Ordinal Logistic Regression
    o	Random Forest
    o	Random Forest Implementation – ranger()
    o	XGBoost
  •	Evaluation Metrics
    o	 Confusion matrix
    o	Area Under the Curve (AUC)
  •	Fix: Converted quality into three groups: (see next project)
    o	Low (≤5)
    o	Medium (=6)
    o	High (≥7)
