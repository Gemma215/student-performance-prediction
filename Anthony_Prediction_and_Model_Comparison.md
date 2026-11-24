# Prediction and Model Comparison

**Name:** Okocha-Ojeah Anthony

**Responsibility:** Explaining how the model makes predictions and how the two models were compared.

**Dependencies:** This part depends on the earlier sections of the group notebook where the dataset was prepared and the Random Forest model was trained.

## 1. Testing a New Student Record

After training the Random Forest model, we tested it with a new student record to see how it would predict a student's performance.

The sample student had the following details:

- **Attendance:** 85%
- **Internal Test 1:** 35
- **Internal Test 2:** 36
- **Assignment Score:** 9
- **Daily Study Hours:** 4.5

These values were entered into the `sample_student` variable and passed to the model using the `predict()` function.

The model predicted that the student's performance category would be **High**.

## 2. Logistic Regression Model

Apart from Random Forest, we also used Logistic Regression to see how another machine learning model would perform on the same dataset.

The Logistic Regression model was trained using the same training data as the Random Forest model so that we could compare their results.

## 3. Comparing the Two Models

After training the Logistic Regression model, we checked its accuracy and compared it with the Random Forest model.

The results were:

- **Random Forest:** 78.75%
- **Logistic Regression:** 81.75%

From the results, Logistic Regression performed better than Random Forest in terms of accuracy, with a difference of 3 percentage points.

This comparison helped us see how the two models performed on the same test data.


