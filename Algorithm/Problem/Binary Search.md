# Binary Search

## Classical Binary Search

Given a target integer T and an integer array A sorted in ascending order, find the index i such that A[i] == T or return -1 if there is no such index.

**Examples**

-   A = {1, 2, 3, 4, 5}, T = 3, return 2
-   A = {1, 2, 3, 4, 5}, T = 6, return -1
-   A = {1, 2, 2, 2, 3, 4}, T = 2, return 1 or 2 or 3



```java
/*
1. Clarification: 
Input:  a target (integer); an array sorted in ascending order(integer)
Output: return index(integer) 
	(1). no index, return -1
	(2). index that a[index] == target, return the index 

2. Assumption:
there are some duplication, and we can return any of the indices i that A[i] == Target

3. Result:
use binarysearch to solve this problem, 
Base case: 
	(1) if (array[i] == target), return i
	(2) if (array[mid] > target), right = mid;
	(3) if (array[mid] < target), left = mid;
	
4. Test:(array, target)
null, => return -1
[""], => return -1
[1], => return 0
[1,1,2,2,2], 2 => return 2,3 or 4
[1,1,2,2], 2 => return 2 or 3
*/

public solution {
    public int binarySearch(int[] array, int target) {
        // corner case
        if (array == null || array.length == 0) {
            return -1;
        }
        
        int left = 0;
        int right = array.length - 1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (array[mid] == target) {
                return mid;
            } else if (array[mid] < target) {
                left = mid + 1;
            } else if (array[mid] > target) {
                right = mid - 1;
            }
        }
        
        return -1;
    }
}
```

|               Time Complexity               | Space Complexity |
| :-----------------------------------------: | :--------------: |
|                   O(logn)                   |       O(1)       |
| each iteration, traversing half of elements |  no extra space  |



|   次数   |                错误                |                           解决方法                           | 注意                 |
| :------: | :--------------------------------: | :----------------------------------------------------------: | -------------------- |
| 1st time | 当array[mid] > target, 弄错 边界了 | <font style = "color: red">应该在base case 阶段过一遍例子！！！</font> | **返回的类型！！！** |





<hr>



## First Occurrence

Given a target integer T and an integer array A sorted in ascending order, find the index of the first occurrence of T in A or return -1 if there is no such index.

**Examples**

-   A = {1, 2, 3}, T = 2, return 1
-   A = {1, 2, 3}, T = 4, return -1
-   A = {1, 2, 2, 2, 3}, T = 2, return 1

```java
/*
1.Clarification:
	(1) input: a target and an array sorted in ascending order
	(2) output: 
		a. return index of the first occurrence of target
		b. no index  => return -1
		
2.Assumption:
	There are some duplicate elements in an array.
	
3.Result
	use binary serach and remain two elements to find the first occurrence of target
	base case: 
		(1) if (array[mid] >= target), right = mid
		(2) if (array[mid] < target), left = mid
	
    index:	0 1 2 3 4 5
			1 2 3 4 4 5 		T: 4
			      l	
			  	    m
					  r
					
4.Test (array, target)
	null => return -1
	[""] => return -1
	[1], 1 => return 0
    [1 2 3 4 4 5], 4 => return 3
    
*/

public Solution {
    public int firstOccur(int[] array, int target) {
        // corner case
        if (array == null || array.length == 0) {
            return -1;
        }
        int left = 0;
        int right = array.length - 1;
        
        while (left < right - 1) {
            int mid = left + (right - left) / 2;
            
            if (array[mid] >= target) {
                right = mid;
            } else if (array[mid] < target) {
                left = mid;
            }
        }
        
        if (array[left] == target) {
            return left;
        }
        if (array[right] == target) {
            return right;
        }
        
        return -1;
    }
}
```



|               Time Complexity               | Space Complexity |
| :-----------------------------------------: | :--------------: |
|                   O(logn)                   |       O(1)       |
| each iteration, traversing half of elements |  no extra space  |





<hr>

## Last Occurrence

Given a target integer T and an integer array A sorted in ascending order, find the index of the last occurrence of T in A or return -1 if there is no such index.

**Examples**

-   A = {1, 2, 3}, T = 2, return 1
-   A = {1, 2, 3}, T = 4, return -1
-   A = {1, 2, 2, 2, 3}, T = 2, return 3

```java
 /*
1.Clarification:
	(1) input: a target and an array sorted in ascending order
	(2) output: 
		a. return index of the last occurrence of target
		b. no index  => return -1
		
2.Assumption:
	There are some duplicate elements in an array.
	
3.Result
	use binary serach and remain two elements to find the first occurrence of target
	
	base case: 
		(1) if (array[mid] > target), right = mid
		(2) if (array[mid] <= target), left = mid
	
    index:	0 1 2 3 4 5
			1 2 3 4 4 5 		T: 4
			      l	
			  	    m
					  r
					
4.Test (array, target)
	null => return -1
	[""] => return -1
	[1], 1 => return 0
    [1 2 3 4 4 5], 4 => return 4
*/

public class Solution {
  public int lastOccur(int[] array, int target) {
     // corner case
        if (array == null || array.length == 0) {
            return -1;
        }
        int left = 0;
        int right = array.length - 1;
        
        while (left < right - 1) {
            int mid = left + (right - left) / 2;
            
            if (array[mid] > target) {
                right = mid;
            } else if (array[mid] <= target) {
                left = mid;
            }
        }

        if (array[right] == target) {
            return right;
        }
        if (array[left] == target) {
            return left;
        }
        
        return -1;
  }
}
```



|               Time Complexity               | Space Complexity |
| :-----------------------------------------: | :--------------: |
|                   O(logn)                   |       O(1)       |
| each iteration, traversing half of elements |  no extra space  |





<hr>





