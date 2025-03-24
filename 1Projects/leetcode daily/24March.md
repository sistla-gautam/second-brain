## 3169

You are given a positive integer `days` representing the total number of days an employee is available for work (starting from day 1). You are also given a 2D array `meetings` of size `n` where, `meetings[i] = [start_i, end_i]` represents the starting and ending days of meeting `i` (inclusive).

Return the count of days when the employee is available for work but no meetings are scheduled.

**Note:** The meetings may overlap.


---
**Example 1:**

**Input:** days = 10, meetings = [[5,7],[1,3],[9,10]]

**Output:** 2

**Explanation:**

There is no meeting scheduled on the 4th and 8th days.

**Example 2:**

**Input:** days = 5, meetings = [[2,4],[1,3]]

**Output:** 1

**Explanation:**

There is no meeting scheduled on the 5th day.

**Example 3:**

**Input:** days = 6, meetings = [[1,6]]

**Output:** 0

**Explanation:**

Meetings are scheduled for all working days.


[[Drawing 2025-03-24 13.24.01.excalidraw]]

---
![[Pasted image 20250324210104.png]]

---
# Solution

```JS
/**

 * @param {number} days

 * @param {number[][]} meetings

 * @return {number}

 */

var countDays = function(days, meetings) {

    meetings.sort((a,b)=>{return a[0]-b[0]})

  

   let total = meetings[0][0] - 1

   let free = meetings[0][1]+ 1

  

   for(let day = 0; day < meetings.length; day++){

    if(meetings[day][0]>free){

        total += meetings[day][0] - free

    }

    free = Math.max(free, meetings[day][1] + 1)

   }

  

   if(free <=days){

    total+=(days - free+1)

   }

   return total

};
```

---
# Logic
### Initial state
- total free is initialized by taking the difference of the first meeting and `1`
	- if any gaps, this will be added to this
	- else, will become zero
- first free day is calculated as the one day after the first meeting end date

### middle state
- if the current iterator start date is higher than the free date, then we take calculate the number of free days and add it
- we update the next free day as one more than the current end date
- if the value is not, then we take the max of the (1 + current end date) and the free date
	- this way, we can find out what is the next free without worrying about falsely updating the total number of days

### end state
- calculate (if any) remaining free days and add them to the total