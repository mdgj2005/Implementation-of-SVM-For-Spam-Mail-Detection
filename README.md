# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. 
2. 
3. 
4. 

## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: M Gokul Anand
RegisterNumber: 212223040049
*/
import chardet
file='spam.csv'
with open (file,'rb') as rawdata:
    result = chardet.detect(rawdata.read(100000))
result
import pandas as pd
data=pd.read_csv("spam.csv",encoding='windows-1252')
data.head()
```
![Screenshot 2025-05-20 112848](https://github.com/user-attachments/assets/679a728e-b6eb-4f73-83e2-fa999a1c8195)
``
`data.info()
```
![445391595-145af677-8d97-456c-959f-c752490dbff7](https://github.com/user-attachments/assets/c6ab109e-4fde-46e7-bf5e-f2f5406c93b5)
```
data.isnull().sum()
```
![445391765-14ca0be9-88b7-406d-9400-b6ecb7ce7f81](https://github.com/user-attachments/assets/7e27682c-7ce2-4d83-b78b-b8d26ca604d3)
```x=data["v1"].values
y=data["v2"].values
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)
from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()
x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)
from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred
```
![445391857-8cdfabfc-6e41-47c5-b376-afa3770cbac8](https://github.com/user-attachments/assets/e174cabe-085d-4333-bf01-cf6f28370912)
```
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```
![445391921-97159524-0d1c-4422-a7fd-28b3ad3cd2c7](https://github.com/user-attachments/assets/2bb599a4-800c-45a4-87e3-aeda51a9f09d)

## Output:
![SVM For Spam Mail Detection](sam.png)


## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
