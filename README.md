Here is a short, concise version of your `README.md` file.

-----

# 🌊 Earthquake & Tsunami Prediction Model

This project analyzes a dataset of strong earthquakes (magnitude 6.5+) to identify key predictors and build a machine learning model to predict tsunami occurrences.

The final **XGBoost Classifier** model achieves **95.5% accuracy** and a **0.93 F1-Score** on the unseen test set.

-----

## 💡 Key Findings from EDA

  * **Location & Depth are Critical:** The most significant predictors of a tsunami are not just magnitude, but a **shallow depth** and an **offshore epicenter** near a known subduction zone.
  * **Temporal Trend:** A notable increase in recorded tsunami-triggering events was observed in the data **after 2012**.
  * **Data Imbalance:** The dataset is imbalanced (39% tsunami events), which was handled using stratified sampling to ensure a reliable model.

-----

## 🚀 Final Model Performance

The model was evaluated on the unseen test set.

| Metric | Score (Test Set) |
| :--- | :--- |
| **Accuracy** | 95.5% |
| **F1-Score (Tsunami=1)** | 0.93 |
| **Precision (Tsunami=1)** | 0.97 |
| **Recall (Tsunami=1)** | 0.90 |

This indicates the model is highly effective at both identifying real tsunamis (high recall) and being correct when it makes a prediction (high precision).

-----

## 📂 Project Structure

```
|   README.md
|   requirements.txt
|
+---.ipynb_checkpoints
|       earthquake_data_tsunami-checkpoint.csv
|       EDA-checkpoint.ipynb
|
+---.vscode
|       settings.json
|
+---data
|   +---processed
|   |       earthquake_data_tsunami.csv
|   |       test_set.csv
|   |       train_set.csv
|   |       valid_set.csv
|   |
|   \---raw
|           raw_earthquake_data_tsunami.csv
|
+---models
|       earthquake_tsunami_XGBClassifier.pkl
|
+---notebook
|   |   1. EDA.ipynb
|   |   2. Preprocess_and_Model.ipynb
|   |   3. Model_building.ipynb
|   |
|   \---.ipynb_checkpoints
|           3. Model_building-checkpoint.ipynb
|           EDA-checkpoint.ipynb
|
\---plots
    +---bivariate_analysis
    |   |   Depth_(km)_vs_Tsunami_boxplot.png
    |   |   Distance_to_Nearest_Station_vs_Tsunami_boxplot.png
    |   |   latitude_vs_Tsunami_boxplot.png
    |   |   longitude_vs_Tsunami_boxplot.png
    |   |   Magnitude_vs_Tsunami_boxplot.png
    |   |   Number_of_Stations_vs_Tsunami_boxplot.png
    |   |   Significance_vs_Tsunami_boxplot.png
    |   |
    |   +---categorical_vs_categorical
    |   |       Month_vs_Tsunami_countplot.png
    |   |       Year_vs_Month_countplot.png
    |   |       Year_vs_Tsunami_countplot.png
    |   |
    |   +---numerical_vs_categorical
    |   |       Azimuthal_Gap_vs_Month_boxplot.png
    |   |       Azimuthal_Gap_vs_Tsunami_boxplot.png
    |   |       Azimuthal_Gap_vs_Year_boxplot.png
    |   |       Community_Determined_Intensity_vs_Month_boxplot.png
    |   |       Community_Determined_Intensity_vs_Tsunami_boxplot.png
    |   |       Community_Determined_Intensity_vs_Year_boxplot.png
    |   |       Depth_(km)_vs_Month_boxplot.png
    |   |       Depth_(km)_vs_Tsunami_boxplot.png
    |   |       Depth_(km)_vs_Year_boxplot.png
    |   |       Distance_to_Nearest Station_vs_Month_boxplot.png
    |   |       Distance_to_Nearest Station_vs_Tsunami_boxplot.png
    |   |       Distance_to_Nearest Station_vs_Year_boxplot.png
    |   |       latitude_vs_Month_boxplot.png
    |   |       latitude_vs_Tsunami_boxplot.png
    |   |       latitude_vs_Year_boxplot.png
    |   |       longitude_vs_Month_boxplot.png
    |   |       longitude_vs_Tsunami_boxplot.png
    |   |       longitude_vs_Year_boxplot.png
    |   |       Magnitude_vs_Month_boxplot.png
    |   |       Magnitude_vs_Tsunami_boxplot.png
    |   |       Magnitude_vs_Year_boxplot.png
    |   |       Modified_Mercalli_Intensity_vs_Month_boxplot.png
    |   |       Modified_Mercalli_Intensity_vs_Tsunami_boxplot.png
    |   |       Modified_Mercalli_Intensity_vs_Year_boxplot.png
    |   |       Number_of_Stations_vs_Month_boxplot.png
    |   |       Number_of_Stations_vs_Tsunami_boxplot.png
    |   |       Number_of_Stations_vs_Year_boxplot.png
    |   |       Significance_vs_Month_boxplot.png
    |   |       Significance_vs_Tsunami_boxplot.png
    |   |       Significance_vs_Year_boxplot.png
    |   |
    |   \---numerical_vs_numerical
    |           correlation_heatmap_numeric_features.png
    |           pairplot_numeric_features.png
    |
    \---univariate_analysis
            Distribution of Azimuthal_Gap.png
            Distribution of Community_Determined_Intensity.png
            Distribution of Depth_(km).png
            Distribution of Distance_to_Nearest Station.png
            Distribution of latitude.png
            Distribution of longitude.png
            Distribution of Magnitude.png
            Distribution of Modified_Mercalli_Intensity.png
            Distribution of Number_of_Stations.png
            Distribution of Significance.png
            Month_class_distribution.png
            Tsunami_class_distribution.png
            Year_class_distribution.png
```

-----

## ⚙️ How to Run

**1. Install dependencies:**

```bash
pip install -r requirements.txt
```

**2. Run the notebooks in order:**

  * `notebooks/1_EDA.ipynb` (Performs analysis, creates processed data)
  * `notebooks/2_Model_Building.ipynb` (Trains the final model, saves it to `models/`)
