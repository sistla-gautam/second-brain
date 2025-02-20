# matrices
#### common topics to know about
- square and rectangle matrices - (different orders)
- determinant - (single value of the matrix)
- trace - (sum of diagonal elements)
- inverse - ($A^{-1}$)
- transpose - (flip the matrix along the diagonal)
- conjugate - (the conjugate of complex numbers are taken)
- tranjugate - (transpose + conjugate)
- diagonal elements 
---
### determinant
- only possible for square matrices
- calculation of sign of the elements = $(-1)^{i+j}$ 
- expand the determinant along the row or column with the most amount of zeros to reduce calculation
- ![[Pasted image 20241208115535.png]]
- Sarrus rule to find the determinant - shortcut to find the determinant
- ![[Pasted image 20241208115849.png]]
- *singular matrix* - matrix with determinant is 0
- *non singular matrix* - matrix with determinant is not 0
- *invertible matrix* - matrix whose inverse exists
	- necessary conditions for inverse
		- det(A) should not be 0 (matrix must be non singular)
- determinant can be found by getting the product of diagonal elements only in such cases
	- ![[Pasted image 20241208121324.png]]
	- upper, lower, diagonal, scalar, identity matrices
---
## inverse of matrix
- 2x2 matrix
	- ![[Pasted image 20241208122809.png]]
- 3x3 matrix
	- use the Serrus method to find the inverse of the matrix
---
## matrix operations
- reversal law
	- ![[Pasted image 20241208155215.png]]
- condition for multiplication
	- number of columns of 1st matrix = number of rows of 2nd matrix
	- matrix multiplication is not commutative (A* B is not the same as B* A)
- condition to find A +- B
	- matrices must be of the same order
- division of matrices does not exist, so we make use of inverse of a matrix
	- multiply both sides by the inverse of the matrix -> this will be the same as dividing the entire equation by the matrix
	- make sure to remember which side to place the operation, as multiplication is not commutative
---
## types of matrices
- symmetric matrix - $A^T=A$ (transpose is the matrix iteself)
- skew symmetric - $A^T=-A$
- hermitian matrix - $A^\theta = A$ (transpose + conjugate is the matrix itself)
- skew hermitian matrix - $A^\theta = - A$
- orthogonal - $AA^T=I$ (matrix and transpose give identity)
- unitary - $AA^\theta = I$ (matrix and conjugate give identity)
- nilpotent - $A^K=0$ where k is the least positive integer
- idenpotent - $A^2 = A$
- involuntary - $A^2 = I$

### some properties of square skew symmetric matrices
- determinant of A will be 
	- 0 if n is odd
	- perfect square if n is even
- sum of all elements will be 0
	- $\Sigma a_{ij} = 0$
### maximum number of elements
- for skew matrix
	- n(n+1)/2
- general expression when matrix is expanded
	- n!

---
## rank of a matrix
- it is the highest order of a non singular submatrix

#### properties of rank
- rank ($A_{m\times n} <= min(m,n)$)
- rank of null matrix is 0
- 1 <= rank($A_{m\times n}$) <= min(m, n)
- rank (A) = rank