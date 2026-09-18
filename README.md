# DriveBuddyAI – Pav Bhaji Classification

## Project Overview

This project was developed as part of the DriveBuddyAI Machine Learning Challenge. The objective is to classify whether an Instagram post is related to Pav Bhaji using the textual metadata associated with the post.

The approach is text-based and does not use image pixels. Instagram captions and tags are processed and used as input features for the classification model.

## Objective

- Prepare and analyse the provided Instagram metadata.
- Identify useful textual features for classification.
- Convert text into numerical features using TF-IDF.
- Compare multiple machine learning models.
- Handle class imbalance during model training.
- Evaluate the final model on unseen test data.

## Dataset

The provided metadata contained 1,500 Instagram records. After matching the metadata with the supplied image labels, 452 records were available for supervised classification.

Class distribution:

- Non-Pav Bhaji: 269
- Pav Bhaji: 183

The data was divided into training and testing sets using an 80:20 stratified split.

## Methodology

The main pipeline used in the project was:

1. Load the Instagram metadata.
2. Match records with the supplied image-based labels.
3. Combine caption and tags into a single text field.
4. Perform basic text preprocessing.
5. Convert text into TF-IDF features using unigrams and bigrams.
6. Apply chi-square feature selection.
7. Train and compare Logistic Regression, Linear SVM and Naive Bayes models.
8. Address class imbalance using class-balanced models.
9. Select the final model based on test-set performance.
10. Analyse the predictions using classification metrics and a confusion matrix.

## Models Compared

The following models were evaluated:

- Logistic Regression
- Linear Support Vector Machine
- Naive Bayes
- Balanced Logistic Regression
- Balanced Linear SVM

The final model used was **Balanced Logistic Regression**.

## Final Test Results

| Metric | Score |
|---|---:|
| Accuracy | 0.626 |
| Precision | 0.527 |
| Recall | 0.784 |
| F1 Score | 0.630 |
| ROC-AUC | 0.654 |

The confusion matrix for the final model was:

| | Predicted Non-Pav Bhaji | Predicted Pav Bhaji |
|---|---:|---:|
| Actual Non-Pav Bhaji | 28 | 26 |
| Actual Pav Bhaji | 8 | 29 |

The model identified 29 of the 37 Pav Bhaji posts in the test set, while 8 Pav Bhaji posts were classified as non-Pav Bhaji.

## Key Observations

The results show that textual metadata contains useful signals for identifying Pav Bhaji-related posts. Using class-balanced Logistic Regression increased the model's ability to identify the positive class, which is reflected in its recall.

However, the dataset available after metadata-label matching is relatively small and contains noisy social-media text. Therefore, the results should be interpreted as a baseline text-classification solution rather than a production-level classifier.

## Limitations

- The classification uses Instagram text metadata rather than image pixels.
- Social-media captions and tags can contain noisy or unrelated terms.
- Only 452 labelled records were available after matching.
- The model may not generalise to posts with very different writing styles or vocabulary.

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- TF-IDF
- Logistic Regression
- Linear SVM
- Naive Bayes

## Submission

This repository contains the notebook used for the DriveBuddyAI Machine Learning Challenge.
