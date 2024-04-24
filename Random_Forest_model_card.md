---
{}
---
language: en
license: cc-by-4.0
tags:
- text-classification
repo: https://github.com/Hierarch123/NLU.git

---

# Model Card for f38903hq-p07229sl-ED

<!-- Provide a quick summary of what the model is/does. -->

This model classifies whether evidence supports a given claim using a Random Forest classifier.


## Model Details

### Model Description

<!-- Provide a longer summary of what this model is. -->

This model is based upon a Random Forest classifier that was trained on over 23K claim-evidence pairs to determine the relevance of evidence to the claim.

- **Developed by:** Haowen Qu and Shuo Li
- **Language(s):** English
- **Model type:** Supervised
- **Model architecture:** Random Forest
- **Finetuned from model [optional]:** TF-IDF Vectorization

### Model Resources

<!-- Provide links where applicable. -->

- **Repository:** [https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html]
- **Paper or documentation:** [https://www.datacamp.com/tutorial/random-forests-classifier-python]

## Training Details

### Training Data

<!-- This is a short stub of information on the training data that was used, and documentation related to data pre-processing or additional filtering (if applicable). -->

Trained on over 23K pairs of claim-evidence data, sourced from diverse domains including news articles, reports, and other forms of written text used to validate claims.

### Training Procedure

<!-- This relates heavily to the Technical Specifications. Content here should link to that section when it is relevant to the training procedure. -->

#### Training Hyperparameters

<!-- This is a summary of the values of hyperparameters used in training the model. -->


      - n_estimators: 100
      - class_weight: balanced
      - random_state: 42
      - max_features (TF-IDF): 5000
      - ngram_range (TF-IDF): (1, 3)
      - max_df (TF-IDF): 0.75
      - min_df (TF-IDF): 5

#### Speeds, Sizes, Times

<!-- This section provides information about how roughly how long it takes to train the model and the size of the resulting model. -->


      - overall training time: 129.76 seconds
      - model size: 59.43 MB

## Evaluation

<!-- This section describes the evaluation protocols and provides the results. -->

### Testing Data & Metrics

#### Testing Data

<!-- This should describe any evaluation data used (e.g., the development/validation set provided). -->

A subset of the development set provided, amounting to 4K pairs.

#### Metrics

<!-- These are the evaluation metrics being used. -->


      - Precision
      - Recall
      - F1-score
      - Accuracy

### Results

The model obtained an F1-score of 74% and an accuracy of 80%.

## Technical Specifications

### Hardware


      - RAM: at least 8 GB
      - Storage: at least 1GB,
      - CPU: Intel Core i5

### Software


      - Scikit-learn 1.2.1
      - Pandas 1.5.3
      - NLTK 3.7
      - Numpy 1.23.5

## Bias, Risks, and Limitations

<!-- This section is meant to convey both technical and sociotechnical limitations. -->

The model may exhibit bias due to class imbalance, as evidenced by lower precision, recall, and F1-score for the minority class . 

## Additional Information

<!-- Any other information that would be useful for other people to know. -->

The hyperparameters were determined by experimentation
      with different values.
