# End-to-End Data Preprocessing Pipeline

This repository contains a complete, structured data preprocessing pipeline built on a real-world marketing dataset.  
The focus is on **data quality, correctness, and reproducibility**, not modeling.

## Pipeline Overview
The preprocessing is implemented as a step-by-step pipeline, with each notebook handling one responsibility.

1. **01_load_and_inspect.ipynb**
   - Load raw dataset
   - Inspect schema, data types, and missing values

2. **02_missing_values_handling.ipynb**
   - Drop rows with excessive missing data (>50%)
   - Impute numerical features using median
   - Impute categorical features using mode

3. **03_outlier_detection.ipynb**
   - Detect outliers using the IQR method
   - Treat outliers by capping extreme values (no row deletion)

4. **04_categorical_encoding.ipynb**
   - Convert date features to datetime
   - One-hot encode categorical variables
   - Prevent feature explosion

5. **05_feature_scaling.ipynb**
   - Standardize numerical features using StandardScaler
   - Exclude identifiers and target variables from scaling

6. **06_preprocessing_pipeline.ipynb**
   - Reproduce the full preprocessing flow end-to-end
   - Perform final validation
   - Export a clean, model-ready dataset

## Dataset
- Real-world marketing campaign dataset
- Mixed numerical, categorical, and date features
- Includes missing values and natural outliers

## Output
- `raw_data.csv` → original dataset  
- `cleaned_data.csv` → fully preprocessed, ML-ready dataset

## Tech Stack
- Python
- Pandas
- scikit-learn

## Key Engineering Decisions
- Each notebook is **independent and reproducible**
- No chained assignments or deprecated pandas patterns
- Business-safe outlier handling (capping instead of deletion)
- Clear separation between raw and processed data

## Purpose
This project reflects how preprocessing is handled in real-world ML workflows before modeling.
