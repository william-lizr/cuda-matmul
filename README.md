# cuda-matmul
Learning to optimize a cuda kernel for matrix multiplication (gemm/level 3 blas)   

Following tutorial by SIBOEHM:  
https://siboehm.com/articles/22/CUDA-MMM  

Link to BLAS (basic linear algebra)  
https://en.wikipedia.org/wiki/Basic_Linear_Algebra_Subprograms#Level_3  

Level 1:  
vector/matrix addition, scalar multiplication  
( scales at O(n) )  

Level 2:  
vector-matrix multiplication  
( scales at O(n^2) )  

Level 3: general matrix multiplication  
matrix-matrix multiplication + addition  
C <- alpha\*A @ B + beta\*C  

Levels:

Kernel	GFLOPs/s	Performance relative to cuBLAS  
1: Naive	309.0	1.3%  
2: GMEM Coalescing	1986.5	8.5%  
3: SMEM Caching	2980.3	12.8%  
4: 1D Blocktiling	8474.7	36.5%  
5: 2D Blocktiling	15971.7	68.7%  
6: Vectorized Mem Access	18237.3	78.4%  
9: Autotuning	19721.0	84.8%  
10: Warptiling	21779.3	93.7%  
0: cuBLAS	23249.6	100.0%  
























