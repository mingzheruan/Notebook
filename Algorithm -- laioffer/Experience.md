# Experience (Aha-moment)

## Binary Search

important: 下面 left = mid + 1 要考虑是否包含了相关元素，不能漏掉元素

loop循环，得考虑是几个元素left < right - 1 考虑不能陷入死循环，

i < j - 1   when search space has 3 or more elements 会导致剩三个元素，左left 右right 中间mid，不会越界

2个会死循环								

​							

target一定不在哪，把那部分排除





Object 上所有的field 都在heap上，field又指向同在field上的数据





## Recursion

1. subproblem
2. recursion role
3. base case

<br>

## Merge Sort (Recursion)

1. subproblem
2. recursion rule
3. base case

<br>

3遍训练法：

1. 第一遍，打code，总结错误
2. 第二遍，自己打，解释算法（不超过两分钟）

<br>



<br>

物理意义：干什么的

## Practice Speaking

### Content

1. explain high-level idea by one sentence
2. explain every important data structure and physical significance of variable
3. explain the algorithm in mid-level, for example, initialization, how to do in each step, terminal condition, and base case + recursive rule
4. time complexity and space complexity

eg: 

So the maxProdut function, take the input length of rope

and return max product of cutting.

<br>

we always assume the length is greater than one,

<br>

and before, we are doing these,  dynamic programming, we have to allocate int array, of size of them plus one 

<br>

for the base case, we are saving index zero and one to zero

......................(one sentence)

for the induction rule

we are using two loops