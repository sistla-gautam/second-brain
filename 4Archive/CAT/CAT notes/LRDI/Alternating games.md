questions are usually of the following type

- a type of question where two players play against each other
- the players on their turn decide how many coins/ matchsticks to choose
- the last person to pick the final one wins
![[Pasted image 20241003065404.png]]

### solution
- we start from n = 1 and decide if we will win the match with that n value
- we then start increasing n value and seeing all the different possibilities with that n value
- we need to check if there is at least one chance of winning - if yes, then the n value is a winning number

from the above example, we have the following solution
- for n = 1, 3, 4, we will win. for n = 2, our opponent will win
- for n = 5, we will see the possible values that we can land on - 4, 2, 1 (since we can only choose 1, 3 or 4 matchsticks)
- since we have 2 as an option, we will win on 5
	- out aim is to get the opponent to get the failing number, so they dont have a chance of winning