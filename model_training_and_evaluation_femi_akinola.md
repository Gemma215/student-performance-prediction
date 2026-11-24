# Model Training and Evaluation

**Name:** Femi Akinola

**Responsibility:** Explaining how the dataset was split, how the Random
Forest model was created and trained, and how its performance was
evaluated.

**Dependencies:** This section depends on the earlier sections of the
group notebook where the dataset was cleaned, prepared, and the target
variable (`Performance`) was defined.

## 1. Splitting the Dataset (80:20)

Before training the model, the dataset was divided into two subsets:
training data and testing data.

The dataset was split using an 80:20 ratio:

-   **80% Training Data:** Used to train the model and allow it to learn
    patterns in the student data.
-   **20% Testing Data:** Used to evaluate the model's performance on
    data it had not seen during training.

The `train_test_split()` function from Scikit-learn was used to perform
the split. A `random_state` value was specified to make the results
reproducible.

``` python
from sklearn.model_selection import train_test_split

X = df.drop('Performance', axis=1)
y = df['Performance']

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42, stratify=y
)
```

Here, `X` contains the input features used to predict student
performance, while `y` contains the target variable, `Performance`.

## 2. Creating and Training the Random Forest Model

After splitting the dataset, we created a Random Forest Classifier using
Scikit-learn.

Random Forest is an ensemble learning algorithm that builds multiple
decision trees and combines their predictions to produce a
classification result.

The model was configured with 100 decision trees and trained using the
training dataset.

``` python
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier(
    n_estimators=100,
    random_state=42
)

model.fit(X_train, y_train)
```

The `fit()` function trained the model using the input features
(`X_train`) and their corresponding performance categories (`y_train`).

## 3. Making Predictions on Test Data

Once the model had been trained, it was used to predict the performance
categories of students in the testing dataset.

The `predict()` function generated predictions using the test features.

``` python
y_pred = model.predict(X_test)
```

The predicted values (`y_pred`) were then compared with the actual
performance categories (`y_test`) to determine how well the model
classified student performance.

## 4. Calculating Accuracy and Classification Report

To evaluate the Random Forest model, we used accuracy and a
classification report from Scikit-learn.

``` python
from sklearn.metrics import accuracy_score, classification_report

accuracy = accuracy_score(y_test, y_pred)

print("Model Accuracy:", accuracy * 100, "%")

print("\nClassification Report:")
print(classification_report(y_test, y_pred))
```

The evaluation metrics provided information about the model's
performance:

-   **Accuracy:** The percentage of all test records correctly
    classified by the model.
-   **Precision:** How many of the records predicted to belong to a
    particular category actually belonged to that category.
-   **Recall:** How many of the actual records in a category were
    correctly identified by the model.
-   **F1-score:** A measure that combines precision and recall.
-   **Support:** The number of actual test records in each category.

The model achieved the following results in the earlier evaluation:

  Performance Category     F1-score
  ---------------------- ----------
  Average                      0.83
  High                         0.65
  Low                          0.81

**Overall Model Accuracy: 78.75%**

These results indicate that the Random Forest model performed reasonably
well overall. It achieved its strongest F1-score for the Average
category, followed by the Low category, while its performance was lower
for the High category.

The results suggest that the model was better at identifying students in
the Average and Low performance categories than those in the High
category.


