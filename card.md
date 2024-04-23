card_data = ModelCardData(
    language='en',
    license='cc-by-4.0',
    tags=['text-classification'],
    # change the line below to specify the URL to your Github/Gitlab repo
    repo="https://github.com/username/project_name",
    ignore_metadata_errors=True)



card = ModelCard.from_template(
    card_data = card_data,
    template_path='COMP34812_modelcard_template.md',

    # and the abbreviation of the relevant track name, e.g., NLI, ED, AV
    model_id = 'username1-username2-track_abbreviation',

    model_summary = '''This model classifies whether evidence supports a given claim using a Random Forest classifier.''',
    model_description = '''This model is based upon a Random Forest classifier that was trained on over 23K claim-evidence pairs to determine the relevance of evidence to the claim.''',
    developers = 'Haowen Qu and Shuo Li',
    model_type = 'Supervised',
    model_architecture = 'Random Forest',
    language = 'English',
    base_model = 'bert-base-uncased',
    training_data = 'Trained on over 23,000 pairs of claim-evidence data, sourced from diverse domains including news articles, reports, and other forms of written text used to validate claims.',
    hyperparameters = '''
      - learning_rate: 2e-05
      - train_batch_size: 16
      - eval_batch_size: 16
      - seed: 42
      - num_epochs: 10''',
    speeds_sizes_times = '''
      - overall training time: 5 hours
      - duration per training epoch: 30 minutes
      - model size: 300MB''',
    testing_data = 'A subset of the development set provided, amounting to 2K pairs.',
    testing_metrics = '''
      - Precision
      - Recall
      - F1-score
      - Accuracy''',
    results = 'The model obtained an F1-score of 67% and an accuracy of 70%.',
    hardware_requirements = '''
      - RAM: at least 16 GB
      - Storage: at least 2GB,
      - GPU: V100''',
    software = '''
      - Transformers 4.18.0
      - Pytorch 1.11.0+cu113''',
    bias_risks_limitations = '''Any inputs (concatenation of two sequences) longer than
      512 subwords will be truncated by the model.''',
    additional_information = '''The hyperparameters were determined by experimentation
      with different values.'''
)

# the following lines will write a markdown (.md) file; this becomes one of your model cards
# change the filename accordingly
with open('my_model_card.md', 'w') as model_card:
  model_card.write(card.content)