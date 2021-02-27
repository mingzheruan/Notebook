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
Input:  a target (integer); an array in ascending order(integer)
Output: return index(integer) 
	(1). no index, return -1
	(2). index that a[index] == target, return the index 

2. Assumption:
there are some duplication, and we can return any of the indices i that A[i] == Target

3. Result:
use binarysearch to solve this problem, 
Base case: 
	(1) if (array[i] == target), return i
	(2) if (array[mid] > target), left = mid;
	(3) if (array[mid] < target), right = mid;
	
4. Test:(array, target)
null, => return array
[""], => return array
[1], => return 1
[1,1,2,2,2], 2 => return 2,3 or 4
[1,1,2,2], 2 => return 2 or 3
*/

public solution {
    public int binarySearch(int[] array, int target) {
        // cornor case
        if (array == null || array.length == 0) {
            return -1;
        }
        
        int left = 0;
        int right = array.length - 1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (array[mid] == target) {
                return mid;
            } else if (array[mid] > target) {
                left = mid + 1;
            } else if (array[mid] < target) {
                right = mid - 1;
            }
        }
        
        return -1;
    }
}
```

|               Time Complexity               | Space Complexity |
| :-----------------------------------------: | :--------------: |
|                    O(n)                     |       O(1)       |
| each iteration, traversing half of elements |  no extra space  |





