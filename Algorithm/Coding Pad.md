# Coding Pad

##  K Closest In Sorted Array

Given a target integer T, a non-negative integer K and an integer array A sorted in ascending order, find the K closest numbers to T in A. If there is a tie, the smaller elements are always preferred.

**Assumptions**

- A is not null
- K is guranteed to be >= 0 and K is guranteed to be <= A.length

**Return**

- A size K integer array containing the K closest numbers(not indices) in A, sorted in ascending order by the difference between the number and T. 

**Examples**

- A = {1, 2, 3}, T = 2, K = 3, return {2, 1, 3} or {2, 3, 1}
- A = {1, 4, 6, 8}, T = 3, K = 3, return {4, 1, 6}



Input: int[] array int target int k  Output: int[] result

corner case: 

array  

Time complexity is O(logn)







```java
quickSelect:

input: int[] array, int target, int left, int right, int k

output int[] result
  
  
  public int[] findKClosest(int[] array, int target, int k) {
  quickSelect();
  int[] result = new int[k];
  for (int i = 0; i < k; i++)
}
```



