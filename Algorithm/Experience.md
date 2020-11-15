# Experience (Aha-moment)

## Binary Search

1. BinarySearch有两个难点：
   1. loop中循环的条件，这决定loop将会留有几个元素，但是有可能陷入死循环(使用left < right - 1这个条件不会陷入死循环，但需要后续判断两个元素的值；如果是left <= right 注意可能陷入死循环)
   2. 在调整mid与right、left的值时，需要注意是否有可能漏掉重要元素

2. BinarySearch中：
   1. 需要想target一定不在哪个区间内，并且排除这部分区域以减少搜索空间

<br>

## Recursion

1. subproblem
2. recursion role
3. base case

<br>

static belong to class, not ot object

<br>

物理意义：干什么的

---------------

## Practice Speaking

### Content

**CART**

1. Clarification
   1. duplicate? It could be
   2.  matrix is ascending order or descending order?       ascending order
   3. Data Structure?  only integer
2. Assumption
   1. size? in memory?
   2. signature? input? int target? output?
   3. corner case?
   4. algorithm? Binary search
   5. Time?
3. Result(code)
4. Test

-------------------------------------------------------------

Clarification

Solution

Coding

Test

<br>

Clarification:

1.  应用题转化为算法题
2.  Input: int array, target: int
    1.  int array: not null, not empty, sorted/ascending/duplicate, positive number
    2.  target: int, positive
3.  Output (index):
    1.  no solution: return -1
    2.  multiple solutionL return any
    3.  一个solution: return index

<br>

Solution

1.  High level: why binary search？ 本质： 执行一套逻辑使得每次的搜索空间是上一次搜索空间的一半
2.  物理意义：过例子（画图）
3.  时空复杂度 

<br>

Coding

<br>

Test

<br>

------------



1. explain high-level idea by one sentence
2. explain every important data structure and physical significance of variable
3. explain the algorithm in mid-level, for example, initialization, how to do in each step, terminal condition, and base case + recursive rule
4. time complexity and space complexity



1.  Document your assumptions
2.  Explain your approach and how you intend to slove the problem
3.  Provide code comments where applicable
4.  Explain the big-O run time complexity of your solution. justfy your answer
5.  Identify andy additional data structures you used and justify why you used them
6.  only provide your best answer to each part of the question.