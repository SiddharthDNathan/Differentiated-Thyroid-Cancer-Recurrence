Report

Data Description and Preprocessing

The dataset consists of 383 entries and 17 columns, covering various clinical and pathological features such as age, gender, smoking history, thyroid function, pathology, and recurrence status. The initial exploration revealed no missing values, but 19 duplicate entries were identified and removed, resulting in 364 unique entries.

Categorical variables were label encoded using the category_encoders library to convert them into numerical form suitable for machine learning algorithms. Given the imbalance in the target variable (Recurred), where the majority class was 'No', we applied Synthetic Minority Over-sampling Technique (SMOTE) to balance the classes. Exploratory Data Analysis

Histograms were plotted for each feature, comparing the distributions between patients with recurrence and without recurrence. These visualizations provided initial insights into the data, although additional plots such as correlation heatmaps and pair plots could have offered deeper understanding. Feature Engineering

Feature scaling was performed using StandardScaler to normalize the data, ensuring that features contributed equally to the model training process. While SMOTE was used to address class imbalance, future work could consider advanced feature selection techniques to enhance the model further.

Model Development and Evaluation

Four machine learning models were developed and evaluated:

**Logistic Regression:**
    Cross-validation accuracy on the training set: 88.03%
    Test set accuracy: 92.23%
    ROC AUC score: 0.9841
    Log loss: 0.1849
    Classification Report:
        Precision: 0.96 (Yes), 0.90 (No)
        Recall: 0.88 (Yes), 0.96 (No)
        F1-score: 0.91 (Yes), 0.93 (No)

**K-Nearest Neighbors (KNN):**
    Test set accuracy: 96.12%
    Classification Report:
        Precision: 0.98 (Yes), 0.96 (No)
        Recall: 0.96 (Yes), 0.98 (No)
        F1-score: 0.97 (Yes), 0.97 (No)

**Decision Tree:**
    Test set accuracy: 95.15%
    Classification Report:
        Precision: 0.92 (Yes), 0.98 (No)
        Recall: 0.98 (Yes), 0.93 (No)
        F1-score: 0.95 (Yes), 0.95 (No)
    ROC AUC score: 0.9528

**Random Forest:**
    Test set accuracy: 100%
    Classification Report:
        Precision, Recall, and F1-score: 1.00 (for both classes)
    ROC AUC score: 1.00

Results

The Random Forest classifier demonstrated perfect performance on the test set, with an accuracy, precision, recall, and F1-score of 100%. However, such perfect results may suggest overfitting, and further validation on a separate dataset would be necessary to confirm its generalizability. Logistic Regression and KNN also performed well, with high accuracy and robust classification metrics. The Decision Tree, while effective, was slightly less accurate than the other models.

Conclusion

This project successfully developed and evaluated multiple models for predicting the recurrence of well-differentiated thyroid cancer. The Random Forest model achieved perfect classification metrics, though its generalizability requires further validation. Logistic Regression and KNN models also showed strong performance, making them viable alternatives.

Future work should focus on enhancing feature engineering, exploring additional models, and validating the models on external datasets to ensure robustness and generalizability. These models have the potential to significantly aid clinicians in predicting thyroid cancer recurrence, leading to better-informed treatment decisions and improved patient outcomes.
