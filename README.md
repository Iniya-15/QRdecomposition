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
### Gram-Schmidt Method
```
import numpy as np
def QR_Decomposition(A):
    A=np.array(A, dtype=float)
    m,n=A.shape
    Q=np.zeros((m, n))
    R=np.zeros((n, n))
     
    for k in range(n):
        u=A[:, k]
        for j in range(k):
            R[j, k]=np.dot(Q[:, j], A[:, k])
            u=u-R[j, k]*Q[:, j]
        R[k, k]=np.linalg.norm(u)
        Q[:, k]=u/R[k, k]
        
    print("The Q Matrix is \n",Q)
    print("The R Matrix is \n",R)
    
a = np.array(eval(input()))
QR_Decomposition(a)






```

## Output

![Screenshot 2025-04-21 020310](https://github.com/user-attachments/assets/f899b23c-e021-48df-bfb9-1ff250b5d74f)



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
