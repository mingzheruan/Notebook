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


## Search In Sorted Matrix I

Given a 2D matrix that contains integers only, which each row is sorted in an ascending order. The first element of next row is larger than (or equal to) the last element of previous row.

Given a target number, returning the position that the target locates within the matrix. If the target number does not exist in the matrix, return {-1, -1}.

**Examples:**

matrix = { {1, 2, 3}, {4, 5, 7}, {8, 9, 10} }

target = 7, return {1, 2}

target = 6, return {-1, -1} to represent the target number does not exist in the matrix.



```java
/*
1. Clarification
input: a matrix sorted in an ascending order, target
output: 
	no index, return {-1, -1}
	index, return {i, j}

2. Assumption
	the given matrix is not null, and has size of N * M, where N >= 0 and M >= 0.
3. Result
	convert 2D array into 1D array and use bianry search to solve this problem
	index	0 1 2
		0	1 2 3
		1	4 5 6
		2	7 8 9
	
4. Test
	{1, 2, 3}, {4, 5, 7}, {8, 9, 10}  T: 5  => return {1, 1}
*/

public Solution {
    public int[] search(int[][] matrix, int target) {
        if (matrix.length == 0 || matrix[0].length == 0) {
            return new int[]{-1, -1};
        }
        int rows = matrix.length;
        int cols = matrix[0].length;
        
        int left = 0;
        int right = rows * cols - 1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            int row = mid / cols;
            int col = mid % cols;
                
            if (matrix[row][col] == target) {
                return new int[]{row, col};
            } else if (matrix[row][col] > target) {
                right = mid - 1;
            } else {
                left = mid + 1;
            }
        }
        return new int[]{-1, -1};
    }
}
```



|               Time Complexity               | Space Complexity |
| :-----------------------------------------: | :--------------: |
|                   O(logn)                   |       O(1)       |
| each iteration, traversing half of elements |    new int[]     |



|   次数   |        错误        | 解决方法 | 注意 |
| :------: | :----------------: | :------: | ---- |
| 1st time | 标之间转换出了问题 | 多想几遍 |      |



<hr>


## Closest In Sorted Array

Given a target integer T and an integer array A sorted in ascending order, find the index i in A such that A[i] is closest to T.

**Examples**

-   A = {1, 2, 3}, T = 2, return 1
-   A = {1, 4, 6}, T = 3, return 1
-   A = {1, 4, 6}, T = 5, return 1 or 2
-   A = {1, 3, 3, 4}, T = 2, return 0 or 1 or 2

```java
/*
1. Clarification
input: a target, an integer array sorted in ascending order
output:
	(1) find target, return index
	(2) no target, return -1;

2. Assumption
	There are some duplicate elements. return any index of A[i] that is closest to target. 
3. Result
	use binary search and gain the closest elements
	base case: 
		(1) if (array[mid] == target) return mid;
		(2) if (array[mid] > target) right = mid;
		(3) if (array[mid] < target) left = mid;
4. Test (int[] array, int target)
	null,   => return -1
    [""],   => return -1
    [1,2,3], 2.6 => return 2
*/

public Solution {
    public int closest(int[] array, int target) {
        // corner case
        if (array == null || array.length == 0) {
            return -1;
        }
        
        int left = 0;
        int right = array.length - 1;
        
        while (left < right - 1) {
            int mid = left + (right - left) / 2;
            
            if (array[mid] == target) {
                return mid;
            } else if (array[mid] > target) {
                right = mid;
            } else {
                left = mid;
            }
        }
        
        if (target - array[left] >= array[right] - target) {
            return right;
        }
        if (target - array[left] < array[right] - target) {
            return left;
        }
        
        return -1;
    }
}
```



|               Time Complexity               | Space Complexity |
| :-----------------------------------------: | :--------------: |
|                   O(logn)                   |       O(1)       |
| each iteration, traversing half of elements |                  |



|   次数   |                       错误                       |                  解决方法                  | 注意 |
| :------: | :----------------------------------------------: | :----------------------------------------: | ---- |
| 1st time | input: [1],1  没有考虑没进入循环且左右相等的情况 | 多列几个测试用例，当写完代码时，心中过几遍 |      |



<hr>
## K Closest In Sorted Array

Given a target integer T, a non-negative integer K and an integer array A sorted in ascending order, find the K closest numbers to T in A. If there is a tie, the smaller elements are always preferred.

**Examples**

-   A = {1, 2, 3}, T = 2, K = 3, return {2, 1, 3} or {2, 3, 1}
-   A = {1, 4, 6, 8}, T = 3, K = 3, return {4, 1, 6}

```java
/*
1. Clarification
input: target, positive Integer K, array sorted in ascending order
output:
	K closest number to target

2. Assumption
	A is not null
	K is guranteed to be >= 0 and K is guranteed to be <= A.length
	
3. Result
	use binary search to find target and move the closest elements into array
	
4. Test(int[] array, int target, int k)
	null, ,  => return array
	[""], ,  => return array
	[1],2,1  => return [1]
	[1,2,3,4],2,3 => return[1,2,3]
*/

public Solution {
    public int[] kClosest(int[] array, int target, int k) {
        // sanity check
         if (array == null || array.length == 0) {
            return array;
        }
        
        if (k == 0) {
            return new int[0];
        }
        
        int left = largestSmallerEqueal(array, target); 
      	int right = left + 1;
        int[] result = new int[k];
        
        for (int i = 0; i < k; i++) {
            if (right >= array.length || left >= 0 && target - array[left] <= array[right] - target) {
                result[i] = array[left--];
            } else {
                result[i] = array[right++];
            }
        }
        return result;
    }
    
    private int largestSmallerEqueal(int[] array, int target) {
        int left = 0;
        int right = array.length - 1;
        while (left < right - 1) {
            int mid = left + (right - left) / 2;
            if (array[mid] <= target) {
                left = mid;
            } else {
                right = mid;
            }
         } 
            if (array[left] <= target) {
                  return left;
              }
            if (array[right] <= target) {
                return right;
            } 
           
            return -1;
    }
}
```





|               Time Complexity               | Space Complexity |
| :-----------------------------------------: | :--------------: |
|                   O(logn)                   |       O(1)       |
| each iteration, traversing half of elements |                  |



|   次数   |              错误              |                  解决方法                  | 注意 |
| :------: | :----------------------------: | :----------------------------------------: | ---- |
| 1st time | 没有考虑当target超出边界的情况 | 多列几个测试用例，当写完代码时，心中过几遍 |      |



<hr>



## Smallest Element Larger than Target

Given a target integer T and an integer array A sorted in ascending order, find the index of the smallest element in A that is larger than T or return -1 if there is no such index.

**Examples**

A = {1, 2, 3}, T = 1, return 1

A = {1, 2, 3}, T = 3, return -1

A = {1, 2, 2, 2, 3}, T = 1, return 1

```java
/*
1. Clarification
input: target, array sorted in ascending order
output:
	(1)  return index 
	(2)  no index, return -1

2. Assumption
	There can be duplicate elements in the array.

3. Result
	use binary search to find target, and select smallest element that is larger than target
		
4. Test(int[] array, int target)
	// corner case
	null,2   => return -1
	[""],2	 => return -1
	// case analysis
									array
							_____|________|____
							  
	[1,2,3],0 => return 0    r	 	 
	[1,2,3],2 => return 2	 		r
	[1 2 3],3 => return -1   				  r
	[1,2,2,3,3,4],2 => return 3
*/

public Solution {
    public int smallestElementLargerThanTarget(int[] array, int target) {
        if (array == null || array.length == 0) {
            return -1;
        }
  
        int result = findTarget(array, target);

        return result;
    }
    
    private int findTarget(int[] array, int target) {
        int left = 0;
        int right = array.length - 1;
        
        while (left < right - 1) {
            
            int mid = left + (right - left) / 2;
            
            if (array[mid] <= target) {
                left = mid + 1;
            } else {
                right = mid;
            }
        }
        
        if (array[left] > target) {
            return left;
        } 
        if (array[right] > target) {
            return right;
        } 
        
        return -1;
    }
}
```



|               Time Complexity               | Space Complexity |
| :-----------------------------------------: | :--------------: |
|                   O(logn)                   |       O(1)       |
| each iteration, traversing half of elements |                  |



<hr>



## Search In Unknown Sized Sorted Array

Given a integer dictionary A of unknown size, where the numbers in the dictionary are sorted in ascending order, determine if a given target integer T is in the dictionary. Return the index of T in A, return -1 if T is not in A.

**Examples**

-   A = {1, 2, 5, 9, ......}, T = 5, return 2
-   A = {1, 2, 5, 9, 12, ......}, T = 7, return -1



```java
/*
1. Clarification
input:	dictionary sorted in ascending order, 	target
output:	return index or reture -1

2. Assumption
	(1) dictionary A is not null
	(2) dictionary.get(i) will return null(Java)/INT_MIN(C++)/None(Python) if index i is out of bounds

3. Result
	get the length of dictionary and use binary search find target

4. Test
		

*/

public Solution {
    public int search(Dictionary dictionary, int target) {
        if (dictionary == null) {
            return -1;
        }
        
        int left = 0;
        int right = 1;
        
        while (dictionary.get(right) != null && dictionary.get(right) < target) {
            left = right;
            right = 2 * right;
        }
        return binarySearch (dictionary, target, left, right);
    }
    
    private int bianrySearch
}


```































```java
/*
1. Clarification
input:
output:

2. Assumption
3. Result
4. Test
*/
```

