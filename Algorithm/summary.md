Time Complexity:

1.  先判断是否存在 callfunction （即是否存在recursion）

2.  

    1.  如果不存在 callfuntion，只需要判断循环次数

    2.  如果存在 callfunction

        1.  先画 recursion tree

        2.  recursion tree 里所有节点的时间复杂度之和（callfunction的层数 * 各自 function 中的时间复杂度）

            

Space Complexity:

1.  分为 stack 和 heap
    1.  stack 
        1.  存在recursion， stack 为 recursion tree 的高度（层数）
        2.  不存在recursion，stack 为 O（1）
    2.  heap 为 每一个 callfunction 中新创建object（即 new object）的空间之和





### Selection Sort

i : 左边（不包含i）已经是排好序的

[i,j) : 已搜索过的区域

j : 右边（包含j）是未搜索区域

1.  在没有排好序的部分找最小值且记录，将最小值和 i 所在位置互换
2.  迭代直到排好所有元素，且剩最后一个元素的时候需要结束



具体步骤：

1.  selection Sort 分为两个循环
    1.  外循环

### Recursion 步骤

1.  base case
2.  recursive rule

### MergeSort

1.  recursion
2.  一分为二，谁小移谁

