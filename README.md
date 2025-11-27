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
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: DHAMODHARAN S
RegisterNumber: 25009463
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,m))
    u=np.empty((n,m))
    R=np.zeros((n,m))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(n):
            u[:,i]-=(A[:,i]@Q[:,j])*Q[:,j]
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])    
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
    print(f"The Q Matrix is\n {Q}")
    print(f"The R Matrix is\n {R}")
    
a=np.array(eval(input()))
QR_Decomposition(a)
```

## Output
<img width="1859" height="969" alt="ex8 ss 1" src="https://github.com/user-attachments/assets/b21a1690-5ca8-4470-bf99-aaf2fdcfb8f2" />
<img width="1862" height="742" alt="ex8 ss2" src="https://github.com/user-attachments/assets/b5aa2737-a1a7-4425-a67a-92b5c6e4564d" />





## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
