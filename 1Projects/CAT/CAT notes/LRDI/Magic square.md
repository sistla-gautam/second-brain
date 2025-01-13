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

### even x even grid
- we start by filling the grid with the values as is
- we swap the elements along the diagonals
for instance

| 1   |     |     | 5   |
| --- | --- | --- | --- |
|     | 2   | 6   |     |
|     | 7   | 3   |     |
| 8   |     |     | 4   |
 will become
 
| 4   |     |     | 8   |
| --- | --- | --- | --- |
|     | 3   | 7   |     |
|     | 6   | 2   |     |
| 5   |     |     | 1   |
> this is not the original way of filling elements, 