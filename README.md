# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
1.Import the required library and read the dataframe.
2.Write a function computeCost to generate the cost function.
3.Perform iterations og gradient steps with learning rate.
4.Plot the Cost function using Gradient Descent and generate the required graph.
```
## Program:
```
/*
Program to implement the linear regression using gradient descent.
Developed by: Abisheik Raj J
RegisterNumber:212224230006  
*/
import numpy as np
import pandas as pd
from sklearn.preprocessing import StandardScaler
def linear_regression(X1,y,learning_rate = 0.1, num_iters = 1000):
    X = np.c_[np.ones(len(X1)),X1]
    theta = np.zeros(X.shape[1]).reshape(-1,1)
    
    for _ in range(num_iters):
        predictions = (X).dot(theta).reshape(-1,1)
        errors=(predictions - y ).reshape(-1,1)
        theta -= learning_rate*(1/len(X1))*X.T.dot(errors)
    return theta
data=pd.read_csv("50_Startups.csv")
data.head()
X=(data.iloc[1:,:-2].values)
X1=X.astype(float)
scaler=StandardScaler()
y=(data.iloc[1:,-1].values).reshape(-1,1)
X1_Scaled=scaler.fit_transform(X1)
Y1_Scaled=scaler.fit_transform(y)
print(X)
print(X1_Scaled)
theta= linear_regression(X1_Scaled,Y1_Scaled)
new_data=np.array([165349.2,136897.8,471784.1]).reshape(-1,1)
new_Scaled=scaler.fit_transform(new_data)
prediction=np.dot(np.append(1,new_Scaled),theta)
prediction=prediction.reshape(-1,1)
pre=scaler.inverse_transform(prediction)
print(prediction)
print(f"Predicted value: {pre}")
```

## Output:
### DATA INFORMATION
![Screenshot 2025-03-15 134140](https://github.com/user-attachments/assets/05c591c0-3e43-4bb2-9ffd-e94d615029e9)
### VALUE OF X
![Screenshot 2025-03-15 133611](https://github.com/user-attachments/assets/fb249c0e-9ed2-4a3d-86b5-66629e0cd46a)
### VALUE OF X1_SCALED
![Screenshot 2025-03-15 133622](https://github.com/user-attachments/assets/126aa0dc-58f1-4324-8c1f-dda5614cf017)
### PREDICTED VALUE
![Screenshot 2025-03-15 133629](https://github.com/user-attachments/assets/f9b8abb3-f92a-4578-bb83-ee0ea9676727)




## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.
