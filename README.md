# NLP & Sentiment Analysis of Product Reviews

## Project Overview

This project uses Natural Language Processing (NLP) and Machine Learning to classify product reviews as **Positive** or **Negative**. The project uses an Amazon product reviews dataset and compares two classification algorithms: Multinomial Naive Bayes and Support Vector Machine (SVM).

## Objectives

- Clean and preprocess text reviews.
- Apply tokenization, stop-word removal, and lemmatization.
- Convert text into numerical features using TF-IDF.
- Train and evaluate sentiment classification models.
- Compare model performance using accuracy and confusion matrices.

## Technologies Used

- Python
- Jupyter Notebook
- Pandas
- NLTK
- Scikit-learn
- Matplotlib

## Dataset

The project uses `amazon_cells_labelled.txt`, containing 1,000 product reviews.

- **0:** Negative review
- **1:** Positive review

The dataset contains 500 negative and 500 positive reviews.

## Methodology

1. **Data Loading:** Load the product reviews into a Pandas DataFrame.
2. **Text Preprocessing:** Convert text to lowercase, tokenize it, remove stop words and non-alphabetic tokens, and apply lemmatization using NLTK.
3. **Train-Test Split:** Split the data into 80% training and 20% testing data, using stratification.
4. **TF-IDF Vectorization:** Convert text into numerical features.
5. **Model Training:** Train Multinomial Naive Bayes and Linear SVM classifiers.
6. **Evaluation:** Compare accuracy, precision, recall, F1-score, and confusion matrices.

## Results

| Model | Test Accuracy |
|---|---:|
| Multinomial Naive Bayes | 75.00% |
| Linear SVM | 76.50% |

Linear SVM achieved the higher test accuracy on this split, correctly classifying 153 out of 200 test reviews. Naive Bayes correctly classified 150 out of 200.

These results are from one train-test split and do not guarantee the same performance on other data.

## Visualizations

The `visualizations/` folder contains:

- `model_comparison.png` — Comparison of model accuracy.
- `sentiment_distribution.png` — Distribution of positive and negative reviews.
- `naive_bayes_confusion_matrix.png` — Naive Bayes classification results.
- `svm_confusion_matrix.png` — SVM classification results.

## Project Structure

```text
project-4-nlp-sentiment-analysis/
├── raw/
│   └── amazon_cells_labelled.txt
├── visualizations/
│   ├── model_comparison.png
│   ├── sentiment_distribution.png
│   ├── naive_bayes_confusion_matrix.png
│   └── svm_confusion_matrix.png
├── Project_4_NLP_Sentiment_Analysis.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

## How to Run

1. Clone or download this repository.
2. Open the project folder in VS Code.
3. Install the required libraries:

   ```bash
   pip install -r requirements.txt
   ```

4. Open `Project_4_NLP_Sentiment_Analysis.ipynb`.
5. Run the notebook cells in order.

The dataset must remain at `raw/amazon_cells_labelled.txt`, matching the file path used in the notebook.

## Conclusion

This project demonstrates a basic NLP sentiment analysis workflow, from text preprocessing and TF-IDF feature extraction to machine learning classification and evaluation. Linear SVM performed slightly better than Multinomial Naive Bayes on the selected test set.