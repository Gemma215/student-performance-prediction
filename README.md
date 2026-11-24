# Student Performance Prediction Using Machine Learning

## Project Summary
This project uses supervised machine learning to predict student academic performance categories (**High**, **Average**, or **Low**) based on key academic and behavioral indicators. We trained and evaluated a **Random Forest Classifier** against a **Logistic Regression** baseline model using a dataset of 2,000 student records[cite: 2]. While the Logistic Regression baseline achieved **81.75% accuracy**, our Random Forest model achieved **78.75% overall accuracy** and **0.86 precision** in accurately flagging "Low" performing students[cite: 2].

## Repository Contents
* `student-performance-prediction.ipynb`: Complete Jupyter Notebook containing data preprocessing, model training, evaluation metrics, and a live sample student prediction block.
* `Final_Marks_Data.csv`: The dataset containing 2,000 student records with features including Attendance (%), Internal Test 1, Internal Test 2, Assignment Score, and Daily Study Hours[cite: 1, 2].
* `requirements.txt`: List of required Python libraries to run the code[cite: 3].

## How to Run the Code
1. Clone this repository or download the files.
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
