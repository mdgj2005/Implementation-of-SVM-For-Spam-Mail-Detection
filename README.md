# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the packages.
2. Analyse the data.
3. Use modelselection and Countvectorizer to preditct the values.
4. Find the accuracy and display the result.
## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: RITHIK V
RegisterNumber:212223230171  
*/

import pandas as pd
data=pd.read_csv("spam.csv", encoding='Windows-1252')
data

data.shape

x=data['v2'].values
y=data['v1'].values
x.shape

y.shape

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2, random_state=0)
x_train

x_train.shape

from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()
x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)
from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred

from sklearn.metrics import accuracy_score,confusion_matrix,classification_report
acc=accuracy_score(y_test,y_pred)
acc

con=confusion_matrix(y_test,y_pred)
print(con)

cl=classification_report(y_test,y_pred)
print(cl)
```



## Output

### data
![image](https://github.com/user-attachments/assets/f82ca49d-d5aa-4373-8b91-35d0e11c50eb)

### data.shape()
![image](https://github.com/user-attachments/assets/dde5ad86-af9a-4342-a5df-ba4533138ea1)

### x.shape()
![image](https://github.com/user-attachments/assets/970c307f-910f-4f97-af72-598528d4fe65)
### y.shape()
![image](https://github.com/user-attachments/assets/8dccaf8b-f13e-48b9-97d0-7f49508da9ac)
### x_train
![image](https://github.com/user-attachments/assets/7b3d22dc-4289-4eb5-8614-d15e80930218)
### x_train.shape()
![image](https://github.com/user-attachments/assets/18105c0f-6620-4e79-a241-74c0c8ad129c)
### y_pred
![image](https://github.com/user-attachments/assets/9faac5cf-92dc-4796-989e-ab09109eda9e)
### acc (accuracy)
![image](https://github.com/user-attachments/assets/26bdd6ed-3c7e-4861-b52a-a5489c1302d7)
### con (confusion matrix)
![image](https://github.com/user-attachments/assets/bc7d87f8-2d4e-44c6-b432-ba485c265491)

### cl (classification report)
![image](https://github.com/user-attachments/assets/f0625d7f-001e-4061-8307-f31ae4a13740)

## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
