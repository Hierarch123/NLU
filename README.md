# Evidence Detection Model using RandomForest

## Project Overview:
This project develops a RandomForest classifier for the task of evidence detection, which is part of the COMP34812 coursework. It involves preprocessing text data, training a RandomForest model, and predicting whether the evidence supports a given claim.

## Installation:
Before running the code, ensure that the following Python packages are installed:
'''bash
pip install pandas scikit-learn nltk joblib
'''

Additionally, you need to download the NLTK stopwords with:
import nltk
nltk.download('stopwords')

## File Descriptions:
- `train.csv` - The training dataset containing claims, evidence, and labels.
- `dev.csv` - The development dataset used for model validation.
- `test.csv` - The test dataset for generating final predictions.
- `rf_classifier.joblib` - Saved RandomForest model after training.

## Preprocessing:
The text data from the claims and evidence columns undergo preprocessing to remove non-alphabetical characters, convert to lowercase, and remove stopwords.

## Model Training:
A RandomForest model is trained with class weight balancing to accommodate label imbalance. The model is saved to a .joblib file for later use.

## Predictions:
The trained model is used to predict the test dataset. Predictions are saved in a CSV file named Group_33_A.csv.

## Evaluations:
The model's performance on the split test set from the training data is printed as a classification report, showing precision, recall, F1-score, and support for each class.