# IoT-Anomaly-Detection
# PCA_IG Hybrid Feature Selection for IoT Anomaly Detection
This repository contains the code for the paper: **"A Hybrid Feature Selection Framework for High Accuracy Low False-Positive IoT Anomaly Detection"**.
We propose PCA_IG, a novel feature selection algorithm that combines Principal Component Analysis (PCA) and Information Gain (IG) to improve IoT anomaly detection. PCA_IG first uses PCA to reduce dimensionality and capture the main data patterns. Then, it applies IG to select the most informative features from the principal components. This approach enhances detection accuracy and reduces false positives.
## Key Benefits
- **Higher Accuracy**: Improves accuracy by 1.71% (binary) and 2.48% (multi-class) compared to baseline models.
- **Lower False Positives**: Reduces false positive rate by 34.2% on average.
- **Better Efficiency**: Reduces feature redundancy and speeds up model training.
## Datasets
We tested on two public IoT security datasets:
- [CIC-IDS2018](https://www.unb.ca/cic/datasets/ids-2018.html)
- [Bot-IoT](https://research.unsw.edu.au/projects/bot-iot-dataset)
## Requirements
- Python 3.7+
- Libraries: scikit-learn, pandas, numpy, xgboost, matplotlib
Install required packages:
```
pip install scikit-learn pandas numpy xgboost matplotlib
```
## How to Run
1. **Prepare the datasets**:
   - Download the datasets from the links above.
   - Place the CSV files in the `data/raw/` folder (create the folder if it doesn't exist).
2. **Preprocess data** (example for CIC-IDS2018):
   ```bash
   python data_processing/cic_ids_loader.py
   ```
3. **Run PCA_IG feature selection and training**:
   ```bash
   python main.py --dataset cic_ids2018 --classifier rf
   ```
   - Options for `--dataset`: `cic_ids2018` or `bot_iot`
   - Options for `--classifier`: `rf` (Random Forest) or `xgb` (XGBoost)
## Output
After running, results will be saved in the `results/` folder, including:
- Feature importance plots
- Confusion matrices
- Performance metrics (accuracy, precision, recall, F1-score, FPR)
