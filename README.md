# Coffee Rating Prediction

This project aims to predict coffee ratings based on various attributes and identified notes. We experiment with three machine learning methods:

- Multi-layer Perceptron (MLP) network using PyTorch
- Decision Tree
- K-Nearest Neighbors (KNN)

The goal is to train models that can accurately predict the rating of coffee samples.

## Project Structure

- `data/` - Contains datasets for training and testing
- `data_preprocessing.ipynb` - Notebook for data cleaning, feature extraction, and preprocessing
- `train_evaluate.ipynb` - Main notebook for model training and evaluation (with cross-validation and plots)

## Data Preprocessing

The `data_preprocessing.ipynb` notebook performs:
- Loading and viewing the data
- Dropping unnecessary columns (e.g., `coffee_id`)
- Custom text preprocessing and tokenization (HTML removal, lowercasing, punctuation/digit removal, stopword removal, stemming)
- Feature extraction using TF-IDF for text and encoding for categorical/numeric features
- Combining all features into a single matrix using `ColumnTransformer`
- Outputting transformed data for model training

## Model Training and Evaluation

- `train_evaluate.ipynb`:
  - Imports and preprocesses the data using the preprocessing notebook
  - Trains and evaluates Decision Tree, KNN, and PyTorch MLP models
  - Supports both simple train/validation splits and 5-fold cross-validation
  - Generates and saves plots (e.g., learning curves, F1 bar charts, confusion matrices) in the `plots/` directory

## How to Run

1. **(Recommended) Create a virtual environment**  
   This is optional but recommended to avoid dependency conflicts:
   ```
   python3 -m venv .venv
   source .venv/bin/activate
   ```

2. **Install dependencies**  
   ```
   pip install -r requirements.txt
   ```

3. **Download NLTK resources**  
   The first run will download required NLTK data (stopwords, punkt).

4. **Run the notebooks**  
   Open JupyterLab or Jupyter Notebook in this directory:
   ```
   jupyter lab
   ```
   or
   ```
   jupyter notebook
   ```
   Then open and run the following notebooks in order:
   1. `data_preprocessing.ipynb`
   2. `train_evaluate.ipynb`

   > **Note:** The training notebook depends on the outputs of `data_preprocessing.ipynb`.

5. **View Results**  
   Generated plots and evaluation results will be saved in the `plots/` directory.

## Notes

- The `plots/` directory is ignored by git.
- Data files should be placed in the `data/` directory.
- For reproducibility, random seeds are set where possible.

More details and instructions will be added as the project progresses.
