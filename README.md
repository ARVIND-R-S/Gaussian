# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
```
1.import os and numpy.
2.Start the program.
3.Read the number of equations, n.
4.Create an augmented matrix a of size \(n \times (n+1)\) and an array x to store the solutions.
5.Read all the coefficients of the equations and their constant values into the augmented matrix.
6.Convert the matrix into an upper triangular matrix using Gaussian elimination.
7.Check whether the diagonal element is zero.
8.If it is zero, display a divide-by-zero error and terminate the program.
9.Calculate the ratio by dividing the element below the diagonal by the diagonal element.
10.Subtract the appropriate multiple of the current row from the rows below it.
11.Calculate the last variable using the last row of the upper triangular matrix.
12.Find the remaining variables using back substitution, starting from the last variable and moving upwards.
13.Print all the variable values rounded to two decimal places.
14.Stop the program. 
```
## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Arvind R S
RegisterNumber: 26017022
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected')
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
    print('X%d = %0.2f' %(i,x[i]),end=' ')
```

## Output:
<img width="407" height="741" alt="ex 6" src="https://github.com/user-attachments/assets/105c5283-5834-4d00-8253-ef8d85040899" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

