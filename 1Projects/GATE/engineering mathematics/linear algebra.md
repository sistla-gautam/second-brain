# matrices
#### common topics to know about
- square and rectangle matrices
- determinant
- trace
- inverse
- transpose
- tranjugate
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