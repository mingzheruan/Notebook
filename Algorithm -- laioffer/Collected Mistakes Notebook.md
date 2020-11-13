# Collected Mistakes Notebook

## 1. BinarySearch

### Code

```java
 		public int[] kClosest(int[] array, int target, int k) {

//        Given a target integer T, a non-negative integer K and an integer array A sorted in ascending order,
//        find the K closest numbers to T in A. If there is a tie, the smaller elements are always preferred.
//
//        Assumptions:
//
//            A is not null
//            K is guranteed to be >= 0 and K is guranteed to be <= A.length
//            Return
//
//            A size K integer array containing the K closest numbers(not indices) in A,
//            sorted in ascending order by the difference between the number and T.
//
//            Examples:
//
//            A = {1, 2, 3}, T = 2, K = 3, return {2, 1, 3} or {2, 3, 1}
//            A = {1, 4, 6, 8}, T = 3, K = 3, return {4, 1, 6}

        // corner case check
        if (array == null || array.length == 0) {
            return array;
        }
        if (k == 0) {
            return new int[0];
        }

        // left is the index of the largest smaller or equal element,
        // right = left + 1
        // These two should be the closest to target.

        int left = largestSmallerEqual(array, target);
        int right = left + 1;
        int[] result = new int [k];
        // this is a typical merge operation

        for (int i = 0; i < k; i++) {
            // we can advance the left pointer when:
            // 1. right pointer is already out of bound.
            // 2. right pointer is not out of bound, left pointer is not out of
            //    bound, and array[left] is closer to target.

            if (right >= array.length || left >= 0 && target - array[left] <= array[right] - target) {
                result[i] = array[left--];
            } else {
                result[i] = array[right++];
            }
        }

        return result;
    }

    private int largestSmallerEqual(int[] array, int target) {
        // find the largest smaller or equal element's index in the array
        int left = 0;
        int right = array.length - 1;
      
      1 2 3 4 5 6 7
      l
            m
									r
        while (left < right - 1)                                                                                                                       
            int mid = left + (right - left) / 2;
            if (array[mid] <= target) {
                left = mid;
            } else {
                right = mid;
            }
        }

        if (array[right] <= target) {
            return right;
        }
        if (array[left] <= target) {
            return left;
        }

        // can not find
        return -1;
    }
   T
1  2  
l
m		
   r
```

<br>

### Important and difficult points: 

1. BinarySearch有两个难点：
   1. loop中循环的条件，这决定loop将会留有几个元素，但是有可能陷入死循环(使用left < right - 1这个条件不会陷入死循环，但需要后续判断两个元素的值；如果是left <= right 注意可能陷入死循环)
   2. 在调整mid与right、left的值时，需要注意是否有可能漏掉重要元素

2. BinarySearch中：
   1. 需要想target一定不在哪个区间内，并且排除这部分区域以减少搜索空间



