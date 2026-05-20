# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
Input the Data

Read the number of equations n.

Input the augmented matrix a[n][n+1].

Perform Forward Elimination

Convert the augmented matrix into an upper triangular matrix using Gaussian elimination.

Check for division by zero during pivot operations.

Perform Back Substitution

Calculate the last variable first
.
Substitute the known values to find the remaining variables.

Display the Solution

Print the values of all unknown variables x₁, x₂, ..., xₙ.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: 
RegisterNumber: 
*/

import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][j]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-1,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f '%(i,x[i]),end="")
    
```

## Output:

<img width="1373" height="841" alt="image" src="https://github.com/user-attachments/assets/c2c94af9-d80f-42f6-a748-8a2990fec622" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

