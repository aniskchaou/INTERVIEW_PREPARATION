# Strassen’s Matrix Multiplication
Given two square matrices A and B of size n x n each, find their multiplication matrix.
**Naive Method**

    void multiply(int A[][N], int B[][N], int C[][N]) 
    { 
        for (int i = 0; i < N; i++) 
        { 
            for (int j = 0; j < N; j++) 
            { 
                C[i][j] = 0; 
                for (int k = 0; k < N; k++) 
                { 
                    C[i][j] += A[i][k]*B[k][j]; 
                } 
            } 
        } 
    } 
[https://www.geeksforgeeks.org/strassens-matrix-multiplication/](https://www.geeksforgeeks.org/strassens-matrix-multiplication/)