# 3394
You are given an integer `n` representing the dimensions of an `n x n` grid, with the origin at the bottom-left corner of the grid. You are also given a 2D array of coordinates `rectangles`, where `rectangles[i]` is in the form `[startx, starty, endx, endy]`, representing a rectangle on the grid. Each rectangle is defined as follows:

- `(startx, starty)`: The bottom-left corner of the rectangle.
- `(endx, endy)`: The top-right corner of the rectangle.

**Note** that the rectangles do not overlap. Your task is to determine if it is possible to make **either two horizontal or two vertical cuts** on the grid such that:

- Each of the three resulting sections formed by the cuts contains **at least** one rectangle.
- Every rectangle belongs to **exactly** one section.

Return `true` if such cuts can be made; otherwise, return `false`.

---
**Example 1:**

**Input:** n = 5, rectangles = [[1,0,5,2],[0,2,2,4],[3,2,5,3],[0,4,4,5]]

**Output:** true

**Explanation:**

![](https://assets.leetcode.com/uploads/2024/10/23/tt1drawio.png)

The grid is shown in the diagram. We can make horizontal cuts at `y = 2` and `y = 4`. Hence, output is true.

**Example 2:**

**Input:** n = 4, rectangles = [[0,0,1,1],[2,0,3,4],[0,2,2,3],[3,0,4,3]]

**Output:** true

**Explanation:**

![](https://assets.leetcode.com/uploads/2024/10/23/tc2drawio.png)

We can make vertical cuts at `x = 2` and `x = 3`. Hence, output is true.

**Example 3:**

**Input:** n = 4, rectangles = [[0,2,2,4],[1,0,3,2],[2,2,3,4],[3,0,4,2],[3,2,4,4]]

**Output:** false

**Explanation:**

We cannot make two horizontal or two vertical cuts that satisfy the conditions. Hence, output is false.

---

![[Pasted image 20250325125349.png]]

---
# explanation
- we go through the horizontal and vertical cases individually
- horizontally
	- we check when is the next free spot by getting the right most point of the rectangles
	- if any rectangle starts at the point or after that, then we increment the counter
	- else, we update the next free counter
- vertically, we do the same thing, just find the higher value than the right most value

---

# Solution
```js
/**

 * @param {number} n

 * @param {number[][]} rectangles

 * @return {boolean}

 */

var checkValidCuts = function(n, rectangles) {

  

    let hcheck = 0

    let hfree = 0

    rectangles.sort((a,b)=>{return a[0]-b[0]})

  

    for(let point = 0; point < rectangles.length; point++){

        if(rectangles[point][0] >= hfree){

            hfree = rectangles[point][2]

            hcheck++

        }else{

            hfree = Math.max(rectangles[point][2], hfree)

        }

  

    }

  

    if(hcheck >2){

        return true

    }

  

    rectangles.sort((a,b)=>{return a[1]-b[1]})

  

    let vcheck = 0

    let vfree = 0

    for(let point = 0; point < rectangles.length; point++){

  

         if(rectangles[point][1] >= vfree){

            vfree = rectangles[point][3]

            vcheck++

        }else{

            vfree = Math.max(rectangles[point][3], vfree)

        }

    }

  

    return vcheck > 2

};```
```
```