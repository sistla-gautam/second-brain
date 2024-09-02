### Triangles
###### centroid
- center point of all the medians (median splits the opposite line into 2 equal halves)
- the centroid splits the median in the ratio 2:1
- divides the area of the triangle into equal pieces
###### orthocenter
- the center point of all the altitudes of the triangle
- sum of angles made by 2 vertices with the orthocenter and the other vertex is 180
- ![[Pasted image 20240824132428.png]]
###### incenter
- the center point of all the angle bisectors
- the angle made by two vertices with the incenter is 90 less than half of the other angle
- ![[Pasted image 20240824133213.png]]
- ![[Pasted image 20240824133223.png]]
###### circumcenter
- center of all the perpendicular bisectors 
- 

- ###### appolonius theorem
	- ![[Pasted image 20240824120920.png]]
	- ![[Pasted image 20240824120934.png]]
	-  if the area of a triangle is x, then the area of a triangle formed by the medians is 3/4 the area of the original triangle 
- distance between circumcenter and incenter
	- $d^2=R(R-2r)$ 
- area of a triangle
	- using semiperimeter
	- using height and base
	- $A=r.s$ (r is inradius, s is semiperimeter)
	- $A=\frac{abc}{4R}$ (R is circumradius, a,b,c are sides)
	- $A=\frac{1}{2}ab.sin(ab)$ 
###### angle bisector theorem
- if we have an angle that is bisector, then we have the following property
- ![[Pasted image 20240824123033.png]]

###### right angle triangles
- for a right angle triangle, we have 
	- 2R = h, where h is the hypotenuse
	- r = s - h, where h is the hypo and s is the semiperimeter 

###### conditions for forming triangles
- based on the sides
	- when we have the sides of a triangle, we have the following condition
	- **diff of two sides < third side < sum of two sides**
- given the perimeter, find the number of distinct triangles
	- if the perimeter is even - nearest integer($\frac{P^2}{48}$)
	- if the perimeter is odd - nearest integer ($\frac{(P+3)^2}{48}$)
- if we need to find the number of scalene triangles, we replace P in the formula with (P-6)
	- if the perimeter is even - nearest integer($\frac{(P-6)^2}{48}$)
	- if the perimeter is odd - nearest integer ($\frac{(P-3)^2}{48}$)
- for a given perimeter, there is only either 1 or 0 equilateral triangles that can be formed
- to find the number of isosceles triangles that can be formed, we find the total number of triangles and subtract scalene and equilateral triangles from it