```java
Given a target integer T, a non-negative integer K and an integer array A sorted in ascending order, find the K closest numbers to T in A. If there is a tie, the smaller elements are always preferred.

Assumptions

A is not null
K is guranteed to be >= 0 and K is guranteed to be <= A.length
Return

A size K integer array containing the K closest numbers(not indices) in A, sorted in ascending order by the difference between the number and T. 
Examples

A = {1, 2, 3}, T = 2, K = 3, return {2, 1, 3} or {2, 3, 1}
A = {1, 4, 6, 8}, T = 3, K = 3, return {4, 1, 6}

public int[] kClosest(int[] array, int target, int k) {
  //corner case check
  if (array == null || array.length == 0) {
    return array;
  }
  if (k == 0) {
    return new int[0];
  }
  
  int left = findSmallerElement(array, target);
  int right = left + 1;
  int[] result = new int[k];
  
  for (int i = 0; i < k; i++) {
    if (target - array[left] <= array[right] - target) {
      result[i] = array[left];
      left = left - 1;
    }
    if (target - array[left] > array[right] - target) {
      result[i] = array[right];
      right = right + 1;
    }
  }
  
  return result;
}

private int findSmallerElement (int array, int target) {
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
  
  if (array[left] == target) {
    return left;
  }
  if (array[right] == target) {
    return right;
  }
}
  
```

1		2		3		4		5		6		null

i < j - 1   when search space has 3 or more elements 会导致剩三个元素，左left 右right 中间mid，不会越界

2个会死循环								

​																

面试注释问题

BQ  

开头部分自我介绍

Jamboard

讲题可以举例子

