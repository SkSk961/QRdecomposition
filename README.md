# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
```
### Gram-Schmidt Method
Program to QR decomposition using the Gram-Schmidt method
Developed by: G.Suman
RegisterNumber: 212223240163


import os
import sys
os.environ["OPENBLAS_NUM_THREADS"] = "1"

import numpy as np

def QR_Decomposition(A):
    A = np.array(A, dtype=float)

    m, n = A.shape

    Q = np.zeros((m, n))
    R = np.zeros((n, n))

    for j in range(n):
        v = A[:, j].copy()

        for i in range(j):
            R[i, j] = np.dot(Q[:, i], A[:, j])
            v = v - R[i, j] * Q[:, i]

        R[j, j] = np.sqrt(np.dot(v, v))
        Q[:, j] = v / R[j, j]

    print("The Q Matrix is")
    print('',Q)
```
## Output
<img width="1180" height="582" alt="image" src="https://github.com/user-attachments/assets/bcbca2a3-6e64-4ea4-9fb4-0b8dfa815cea" />




## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
