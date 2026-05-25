# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Read the number of unknowns and the elements of the augmented matrix from the input.
2.Apply forward elimination to convert the matrix into an upper triangular form by eliminating the elements below the pivot.
3.Perform back substitution starting from the last equation to calculate the values of the unknown variables.
4.Print the values of the variables (X0, X1, X2, …) as the final solution. 
 

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by:Manigandan S
RegisterNumber: 212225100025
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
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f ' %(i,x[i]),end="")
```

## Output:

![alt text](<2026-05-25 (1).png>)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

