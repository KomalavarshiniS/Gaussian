# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

Step 1: Import the necessary modules:
Step 2: Read the number of unknowns n from the user.
Step 3: Initialize two arrays:
Step 4: Input the coefficients and constants of the equations into the augmented matrix a.
Step 5: Perform Forward Elimination to convert the augmented matrix into upper triangular form:
Step 6: Perform Back Substitution to compute the values of the unknowns:
Step 7: Print the solution for each variable with two decimal places.
Step 8: End the program.

## Program:
```
'''
Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: KOMALAVARSHINI.S
RegisterNumber: 212224230133
'''
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divde by zero detected!')
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
    print('X%d = %0.2f'%(i,x[i]),end=' ')

```    
    

## Output:
![alt text](<Screenshot 2025-04-17 141936.png>)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

