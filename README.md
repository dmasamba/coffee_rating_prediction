# Coffee Rating Prediction

This project aims to predict coffee ratings based on various attributes and identified notes. We will experiment with three machine learning methods:

- Multi-layer Perceptron (MLP) network using PyTorch
- Decision Tree
- K-Nearest Neighbors (KNN)

The goal is to train models that can accurately predict the rating of coffee samples.

## Project Structure

- `data/` - Contains datasets for training and testing
- `train.ipynb` - Main notebook for model training and evaluation
- `data_preprocessing.ipynb` - Notebook for data cleaning, feature extraction, and preprocessing

## Data Preprocessing

The `data_preprocessing.ipynb` notebook performs:
- Loading and viewing the data
- Dropping unnecessary columns (e.g., `coffee_id`)
- Custom text preprocessing and tokenization (HTML removal, lowercasing, punctuation/digit removal, stopword removal, stemming)
- Feature extraction using TF-IDF for text and encoding for categorical/numeric features
- Combining all features into a single matrix using `ColumnTransformer`
- Outputting transformed data for model training

## Getting Started

More details and instructions will be added as the project progresses.
