# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import the required libraries for data handling, plotting, and Decision Tree classification.

2.Load the Employee dataset and convert categorical data into numerical format using get_dummies().

3.Split the dataset into input features (X) and target output (y), then divide the data into training and testing sets.

4.Create and train the DecisionTreeClassifier model using the training data, then predict the output for test data.

5.Calculate the accuracy of the model and display the Decision Tree diagram using plot_tree().

Program:

## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

#Ex 08 - Implementation of Decision Tree Classifier Model for Predicting Employee Churn
# Import libraries
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder
from sklearn.tree import DecisionTreeClassifier, plot_tree
from sklearn.metrics import accuracy_score, confusion_matrix

df = pd.read_csv("Employee.csv")

label = LabelEncoder()

df['Work_accident'] = label.fit_transform(df['Work_accident'])
df['promotion_last_5years'] = label.fit_transform(df['promotion_last_5years'])
df['Departments '] = label.fit_transform(df['Departments '])
df['salary'] = label.fit_transform(df['salary'])
df['left'] = label.fit_transform(df['left'])

X = df[['satisfaction_level',
        'last_evaluation',
        'number_project',
        'average_montly_hours',
        'time_spend_company']]

y = df['left']

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

model = DecisionTreeClassifier()

model.fit(X_train, y_train)

y_pred = model.predict(X_test)

print("Accuracy:", accuracy_score(y_test, y_pred))

print("Confusion Matrix:")
print(confusion_matrix(y_test, y_pred))

plt.figure(figsize=(12,8))

plot_tree(model,
          feature_names=X.columns,
          class_names=['Stay', 'Left'],
          filled=True)

plt.title("Employee Churn Decision Tree")

plt.show()

Developed by: Swathi P N
RegisterNumber:  212225230279
*/
```

## Output:

![alt text](ml8.1.png)

![alt text](ml8.2.png)

![alt text](ml8.3.png)

## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
