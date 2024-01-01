# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
![Screenshot 2024-01-01 234748](https://github.com/dharshanpt/QRdecomposition/assets/138849376/9b2d62d6-a982-49a9-863e-1a92a91fbde9)

## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by:DHARSHAN PT
RegisterNumber:23005803
'''
import numpy as np
def QR_Decomposition(A):
    n, m = A.shape
    
    Q = np.empty((n, n))
    u = np.empty((n, n))
    
    u[:, 0] = A[:, 0]
    Q[:, 0] = u[:, 0] / np.linalg.norm(u[:, 0])

    for i in range(1, n):
         
        u[:, i] = A[:, i]
        for j in range(i):
            u[:, i] -= (A[:, i] @ Q[:, j]) * Q[:, j]
            
        Q[:, i] = u[:, i] / np.linalg.norm(u[:, i])
        
    R = np.zeros((n, m))
    for i in range(n):
        for j in range(i, m):
            R[i, j] = A[:, j] @ Q[:, i]
    print(Q)
    print(R)
a = np.array(eval(input()))
QR_Decomposition(a)
```

## Output
![Screenshot 2024-01-01 234606](https://github.com/dharshanpt/QRdecomposition/assets/138849376/d816cfd6-9564-4756-a3e3-0a3d6cf07c66)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
