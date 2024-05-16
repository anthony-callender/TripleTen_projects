# The Film Junky Union: Sentiment Analysis Project

## Project Overview

The Film Junky Union is an edgy community for classic movie enthusiasts. This project aims to develop a system for filtering and categorizing movie reviews by training a model to automatically detect negative reviews. Using a dataset of IMDB movie reviews with polarity labeling, the goal is to build a model that classifies reviews as positive or negative, achieving an F1 score of at least 0.85.

## Table of Contents

- [Project Instructions](#project-instructions)
- [Data Description](#data-description)
- [Requirements](#requirements)
- [Setup](#setup)
- [Project Workflow](#project-workflow)
- [Results](#results)
- [Conclusion](#conclusion)
- [Acknowledgements](#acknowledgements)

## Project Instructions

1. **Load the data**.
2. **Preprocess the data**, if required.
3. **Conduct Exploratory Data Analysis (EDA)** and make conclusions on class imbalance.
4. **Preprocess the data for modeling**.
5. **Train at least three different models** for the training dataset.
6. **Test the models** on the test dataset.
7. **Compose a few of your own reviews** and classify them with all the models.
8. **Check for differences** between the testing results of the models and explain them.
9. **Present your findings**.

## Data Description

The dataset, `imdb_reviews.tsv`, includes:

- **review**: The review text.
- **pos**: The target, '0' for negative and '1' for positive.
- **ds_part**: 'train'/'test' for the train/test part of the dataset, respectively.

The data was provided by Andrew L. Maas, Raymond E. Daly, Peter T. Pham, Dan Huang, Andrew Y. Ng, and Christopher Potts. (2011). Learning Word Vectors for Sentiment Analysis. The 49th Annual Meeting of the Association for Computational Linguistics (ACL 2011).

## Requirements

- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- nltk

## Setup

1. **Clone the repository**:
    ```bash
    git clone https://github.com/yourusername/film-junky-union-nlp.git
    ```
2. **Navigate to the project directory**:
    ```bash
    cd film-junky-union-nlp
    ```
3. **Install the required packages**:
    ```bash
    pip install -r requirements.txt
    ```

## Project Workflow

1. **Load the data**: Read the dataset using pandas.
2. **Preprocess the data**: Clean and prepare the data for analysis.
3. **Exploratory Data Analysis (EDA)**: Visualize and understand the data, particularly focusing on class imbalance.
4. **Data Preprocessing for Modeling**: Tokenize, remove stop words, and vectorize the text data.
5. **Model Training**:
    - Train at least three different models (e.g., Logistic Regression, Gradient Boosting, and another of your choice).
    - Evaluate models using cross-validation and select the best performing model.
6. **Model Testing**: Evaluate the selected models on the test dataset.
7. **Custom Review Classification**: Classify a few custom reviews and compare results across models.
8. **Results Analysis**: Analyze the differences between model performances and explain them.
9. **Presentation**: Summarize findings and present results.

## Results

- The best model achieved an F1 score of 0.87 on the test dataset.
- Logistic Regression, Gradient Boosting, and a Random Forest model were compared, with Gradient Boosting performing the best.
- Custom reviews were classified consistently across all models, with minor variations.

## Conclusion

The project successfully developed a system to classify movie reviews as positive or negative, achieving an F1 score above the target of 0.85. The Gradient Boosting model proved to be the most effective, highlighting the potential of ensemble methods in sentiment analysis tasks.

## Acknowledgements

Special thanks to Andrew L. Maas, Raymond E. Daly, Peter T. Pham, Dan Huang, Andrew Y. Ng, and Christopher Potts for providing the dataset and their research on sentiment analysis.
