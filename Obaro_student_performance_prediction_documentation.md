# Student Performance Prediction: Data Preparation & Setup

## 1. Importing the Libraries
* **`pandas` (`pd`)**: Used to load, inspect, and manipulate tabular data (like your CSV dataset in a DataFrame).
* **`train_test_split`**: Splits your dataset into a training set (to teach the model) and a testing set (to evaluate how well it generalizes to unseen data).
* **`RandomForestClassifier`**: The machine learning model itself—an ensemble of decision trees used for classification tasks.
* **`accuracy_score` and `classification_report`**: Evaluation tools used to measure overall accuracy as well as class-by-class precision, recall, and F1-score.

## 2. Loading the CSV Dataset
* `df = pd.read_csv("Final_Marks_Data.csv")` reads the CSV file into a pandas DataFrame called `df`.
* This dataset contains **2,000 entries** of student records, including study metrics and exam marks.

## 3. Creating the Performance Categories
* Because the raw `Final Exam Marks (out of 100)` column is numerical, the `categorize_performance(marks)` function converts those continuous scores into three discrete classes:
  * **`'High'`**: marks `>= 75`
  * **`'Average'`**: marks from `55` up to `74` (`>= 55` and `< 75`)
  * **`'Low'`**: marks `< 55`
* Applying this function across the `Final Exam Marks (out of 100)` column creates a new column, `df['Performance_Category']`, which serves as the classification label.

## 4. Selecting Input Features and Target Variable
* **Input features (`x`)**: The 5 predictor columns used by the model to make predictions—`Attendance (%)`, `Internal Test 1 (out of 40)`, `Internal Test 2 (out of 40)`, assignment score (out of 10), and `Daily Study Hours`.
* **Target variable (`y`)**: `df['Performance_Category']`, which is the output category (`High`, `Average`, or `Low`) the Random Forest model is trained to predict.