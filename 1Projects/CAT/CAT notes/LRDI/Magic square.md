- nxn grid filled with consecutive integers which has
	- same sum along row, column and diagonal
- works only for n * n grid
- the number only need to be consecutive. they need not start from 1 necessarily

### odd x odd grid
- always start from the middle element in the top most row
- go diagonally top right direction
- if the diagonal is blocked, go immediate below to place the element
	- once placed, continue with the diagonal path
- wrap around the box