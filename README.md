# Coffee Rating Prediction

This project predicts coffee ratings (Outstanding vs. Average) using machine learning models based on coffee attributes and review notes.

## Project Structure

- `data/` — Place your raw data files here (e.g., `X_train.csv`, `y_train.csv`, `X_test.csv`). **These CSV files are now tracked in git.**
- `data_preprocessing.ipynb` — Data cleaning, feature engineering, and transformation pipeline.
- `train_evaluate.ipynb` — Main notebook for model training, cross-validation, and evaluation (including plots).
- `test.ipynb` — Loads the best model and generates predictions on the test set.
- `insights_gathering.ipynb` — Analyzes predictions and generates insight plots (e.g., top notes, country, roaster, price).
- `plots/` — Saved plots from training and evaluation (ignored by git).
- `insight_plots/` — Saved plots from insights/analysis (ignored by git).
- `results/` — Output predictions (e.g., `result.csv`) (ignored by git).
- `models/` — Saved model files (ignored by git).
- `.gitignore` — Ignores model files, results, and plot directories.
- `requirements.txt` — Python dependencies.

## Data

- The `data/` folder contains all required CSV files for training and testing:
  - `X_train.csv`, `y_train.csv`, `X_test.csv`
- These files are now included in the repository and will be pushed to git.

## Data Preprocessing

- Loads train/test data from `data/`.
- Drops `coffee_id` (kept separately for output).
- Custom text preprocessing: HTML removal, lowercasing, punctuation/digit removal, stopword removal, stemming.
- Feature extraction:
  - TF-IDF + feature selection for review text.
  - One-hot encoding for categorical features.
  - Log-transform and scaling for price.
- Combines all features using `ColumnTransformer`.
- Outputs transformed data for modeling.

## Model Training and Evaluation

- `train_evaluate.ipynb`:
  - Imports and preprocesses data.
  - Trains and evaluates Decision Tree, KNN, and PyTorch MLP models.
  - Supports both simple train/validation split and 5-fold cross-validation.
  - Saves trained models to `models/`.
  - Generates and saves plots: learning curves, F1 bar charts, confusion matrices.

## Model Selection and Testing

- `test.ipynb`:
  - Loads the best model (based on mean validation F1 from CV).
  - Runs the model on the test set and saves predictions to `results/result.csv`.

## Insights and Analysis

- `insights_gathering.ipynb`:
  - Analyzes predictions in `results/result.csv` and test data.
  - Plots:
    - Top 5 most frequent notes for each class.
    - Class distribution by country of origin.
    - Top roasters for each class.
    - Class distribution by price range.
  - Plots are saved in `insight_plots/`.

## How to Run

1. **Create a virtual environment (recommended):**
   ```
   python3 -m venv .venv
   source .venv/bin/activate
   ```

2. **Install dependencies:**
   ```
   pip install -r requirements.txt
   ```

3. **Download NLTK resources (first run):**
   The notebooks will download required NLTK data (stopwords, punkt) automatically.

4. **Run the notebooks in order:**
   ```
   jupyter lab
   ```
   or
   ```
   jupyter notebook
   ```
   Then run:
   1. `data_preprocessing.ipynb`
   2. `train_evaluate.ipynb`
   3. `test.ipynb`
   4. `insights_gathering.ipynb`

   > **Note:** Each notebook depends on the outputs of the previous one.

5. **View Results:**
   - Model evaluation plots: `plots/`
   - Test predictions: `results/result.csv`
   - Insights/analysis plots: `insight_plots/`

## Notes

- The `data/` folder now contains the actual CSV files, which are tracked in git.
- All generated outputs (plots, results, models) are ignored by git.
- The best model is automatically selected based on cross-validation F1.

---

For questions or improvements, please open an issue or pull request.
