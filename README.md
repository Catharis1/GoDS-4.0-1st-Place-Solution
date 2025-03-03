# GODS 4.0 Hackathon - Mental Health Text Classification

This repository contains the 1st place solution for the GODS 4.0 Hackathon, where the objective was to classify text entries from online discussions into mental health-related categories. The solution involves a combination of classical NLP techniques and advanced transformer-based models to achieve robust performance.

## Solution Workflow

### 1. Data Preprocessing
- **Text Concatenation**: The title and content of each text entry were concatenated.
- **Preprocessing**: Basic text preprocessing steps were applied to clean and prepare the input data.

### 2. Model Training
Two main approaches were used for modeling:

#### a. Classical NLP Approach
- **TF-IDF Vectorization**: The concatenated text was transformed using TF-IDF vectorization.
- **Logistic Regression**: A Logistic Regression model was trained on the TF-IDF vectors.

#### b. Transformer-Based Approach
- **Model**: DebertaV3 Base and Large models were used.
- **Tokenization**: The concatenated text was tokenized, with special tokens added for separation.
- **Mean Pooling**: Mean pooling was applied to the transformer outputs.
- **Training**: The models were trained using advanced optimization strategies, including mixed precision and gradient accumulation.

### 3. Cross-Validation and Ensemble
- **StratifiedKFold**: 5-fold stratified cross-validation was used to validate the models.
- **Ensemble Strategy**: A robust but simple ensemble strategy was employed, combining the predictions from different models.
- **Weight Optimization**: Final weights for the ensemble were optimized based on out-of-fold predictions.

### 4. Final Submission
- **Models Used**:
  - DebertaV3 Base (CV: 0.791)
  - DebertaV3 Large (CV: 0.795)
  - Logistic Regression (CV: 0.75)
- **Ensemble**: The final submission was an ensemble of the above models, with weights optimized for the best performance.

For more details, refer to the [Jury Presentation](./jury-presentation.pdf).
