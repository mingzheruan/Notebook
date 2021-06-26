### 面试要求：

A complete answer will include the following:

1.  Document your assumptions
2.  Explain your approach and how you intend to solve the problem
3.  Provide code comments where applicable
4.  Explain the big-O run time complexity of your solution. Justify your answer
5.  Identify any additional data structures you used and justify why you used them
6.  Only provide your best answer to each part of the question



### Time Complexity:

1.  先判断是否存在 callfunction （即是否存在recursion）

2.  

    1.  如果不存在 callfuntion，只需要判断循环次数

    2.  如果存在 callfunction

        1.  先画 recursion tree
2.  recursion tree 里所有节点的时间复杂度之和（callfunction的层数 * 各自 function 中的时间复杂度）
        


### Space Complexity:

1.  分为 stack 和 heap
    1.  stack 
        1.  存在recursion， stack 为 recursion tree 的高度（层数）
        2.  不存在recursion，stack 为 O（1）
    2.  heap 为 每一个 callfunction 中新创建object（即 new object）的空间之和



***Binary Search题思考流程:***

**针对找target的步骤:**

1.  判断array[mid]是否在搜索空间内
    1.  如果**在**搜索空间内（不可以将array[mid] 排除到搜索空间外），那么 mid **不可以** + 1 、 - 1
    2.  如果**不在**搜索空间内，那么 mid **可以** + 1 、 - 1
2.  根据1 的结果判断
    1.  如果mid 可以并且使用 + 1 、 - 1，left <= right or left < right - 1 都可以用
    2.  如果mid 不可以 + 1 、 - 1，left <= right 就不能用，会陷入死循环，必须用 left < right - 1
3.  所有使用 left < right - 1 都必须考虑 post-processing （即考虑array[left],array[right]元素）
    +   根据最终所求值的关系，判断 array[left],array[right] 元素和target的大小

Note: 

+   如果使用 left <= right， 因为只会留下一个元素，所以可以if (array[mid] == target) {return mid}

**针对可搜索空间的判断步骤:**

1.  1.  target 在可搜索空间的**左边**
    2.  target 在可搜索空间的**中间**
    3.  target 在可搜索空间的**右边**
2.  因题而异，然后考虑通过 binary search 得到的返回值和可搜索空间的关系继续解题



### Selection Sort

Physical Significance

i : 左边（不包含i）已经是排好序的

[i,j) : 已搜索过的区域

j : 右边（包含j）是未搜索区域

1.  在没有排好序的部分找最小值且记录，将最小值和 i 所在位置互换
2.  迭代直到排好所有元素，且剩最后一个元素的时候需要结束

具体步骤：

1.  selection sort 分为两个循环
    1.  外循环：循环（找最小值）的次数
    2.  内循环：在未sort区间找最小值

### Recursion 步骤

1.  base case
2.  recursive rule

### MergeSort

1.  recursion
2.  一分为二，谁小移谁



**Delete in BST 步骤:**
High level:

1.  find target
2.  delete target	

mid level:

1.  find target

    1.  当前值比target大， 进入左子树
    2.  当前值比target小，进入右子树
    3.  直到找到target，进入delete步骤

2.  delete target

    1.  target 没有左子树并且没有右子树，return 右子树（null）

    2.  target 没有左子树并且有右子树，return 右子树

    3.  target 有左子树并且没有右子树，return 左子树

    4.  target 有左子树并且也有右子树，但target的右孩子没有左子树，所以先把target左子树挂到 target 的右孩子的左子树上，return target 的右子树

    5.  target 的 node 有左子树并且也有右子树，但target的右孩子有左子树，所以先在target的右孩子的左子树上找最小值。

        1.  当找到最小值时，把最小值的右子树挂到最小值的父亲的左子树上
        2.  return 最小值，然后
            1.  最小值的左子树连到target的左子树
            2.  最小值的右子树连到target的右子树
            3.  return 当前node

        

问题 Linked List  while 循环条件问题

while(cur1 != null) {
	cur1 = cur1.next;
}

while(cur2.next != null) {
	cur2 = cur2.next;
}

while(cur3.next != null && cur3.next.next != null) {
	cur3 = cur3.next;
}

n1 -> n2 -> n3 -> n4 -> null   (even)
		           cur1
                            cur2
                   cur3

n1 -> n2 -> n3 -> null  (odd)
        cur3         
