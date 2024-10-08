questions are of the following type

given is a table that shows the number of students that are in 5 different classes across 2022 and 2023
we need to calculate the number of students who passed every grade and the number who failed in every grade
Assume that the maximum number of students will pass through each class
![[Pasted image 20241008060825.png]]

##### Solution
- in such cases, we start with the assumption that all the students from class 5 passed (maximum number of students passed through)
- we now back track the number of students who would have failed in the consequent years

assume 5th grade 2022, all 43 passed, then we get
- 43 + 4 are in 6th grade 2023.
- 46 + 4 people are in 6th grade in 2022 (the number of fails will back track)
- which means, 46 people have passed from 6th grade 2022 to 7th grade 2023
- ==but, there are only 44 people in 7th grade 2023==, hence, we reduce the number of pass outs from the starting by 2 (43 people do not pass from 5th grade, only 41 do)
- using this, we get the following table

| **Class** | **2022 Pass** | **2022 Fail** | **2022 Total** | **2023 New** | **2023 Old** | **2023 Total** |
| --------- | ------------- | ------------- | -------------- | ------------ | ------------ | -------------- |
| 5         | 41            | 2             | 43             | 44           | 2            | 46             |
| 6         | 44            | 6             | 50             | 41           | 6            | 47             |
| 7         | 45            | 0             | 45             | 44           | 0            | 44             |
| 8         | 39            | 7             | 46             | 45           | 7            | 52             |
| 9         | 38            | 12            | 50             | 39           | 12           | 51             |
| 10        | 48            | 1             | 49             | 38           | 1            | 39             |
> - split the previous years in pass, fail, total, and the subsequent years into incoming, old and total
> - this is also helpful for other higher order questions which would involve more number of transitions

