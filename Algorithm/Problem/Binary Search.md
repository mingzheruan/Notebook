# Classical Binary Search

Given a target integer T and an integer array A sorted in ascending order, find the index i such that A[i] == T or return -1 if there is no such index.

**Examples**

-   A = {1, 2, 3, 4, 5}, T = 3, return 2
-   A = {1, 2, 3, 4, 5}, T = 6, return -1
-   A = {1, 2, 2, 2, 3, 4}, T = 2, return 1 or 2 or 3



```java
/*
1. Clarification: 
Input:  a target (integer); an array in ascending order(integer)
Output: return index(integer) 
	(1). no index, return -1
	(2). index that a[index] == target, return the index 

2. Assumption:
there are some duplication, and we can return any of the indices i that A[i] == Target

3. Result:
use binarysearch to solve this problem, 
Base case: if (A[i] == target), return i

4. Test:(array, target)
null, return null
[""], return null
*/
```



