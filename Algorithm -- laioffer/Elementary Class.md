### Primitive Types and Basic Operations

#### Primitive Types

byte -- short -- int -- long -- float -- double -- char -- boolean

byte -> short -> int -> long -> float -> double

------------------------------------------------------------>

&nbsp;		&nbsp;&nbsp;&nbsp;		&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;				&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Widening (精度)

it is okay to cast lower precision type to higher precision type implicitly. 

not from high precision type to lower precision type. Java will always help you to perform casting to higher precision if needed

```diff
 if you are not sure, always use explicit conversion!!!
```

  <br>

#### Operators and Precedence

+ bitwise AND ---- & 

+ bitwise inclusive ---- |	     

   <br>		

  Example: 

  if( foo() & goo() ) ---- two function both run.
  
  if( foo() | goo() ) ---- two function both run.

 <br>

+ logical AND ---- &&

+ logical OR ---- ||

   <br>

  Example:

  if( foo() && goo() ) ---- if foo() is false, the judgement is over. no run goo()
  
  if( foo() || goo() ) ---- if foo() is true, the judgement is over. no run goo()

 <br>

### Array, Class and Objects

+ You must specify the length of the array.
+ List, ArrayList, LinkedList are different to arrays!

```
The length cannot be changed after creation
```

 </br>

+ **Declaration**: associate a variable name with an object type

```java
Student firstStudent
```

 </br>

+ **Instantiation**: the new keyword is a java operator that creates the object

```\java
firstStudent = new student

//create an object in the memory and return its refernece to firstStudent
```

 </br>

+ **Initialization**: the new operator is followed by a call to a constructor, which initializes the new object

 </br>

### Object Memory Layout

#### Memory spaces in a java program: Stack and Heap

+ **Stack**: In computer science, a call stack is a stack data structure that stores information about the active subroutines of a computer program(stack frame). This kind of stack is also known as an execution stack, program stack, ccontrol stack, run-time stack, or machine stack, and is often shortened to just "the stack" 

 </br>

+ **Heap**: Java objects reside in an area called the heap. The heap is created when the JVM starts up and may increase or decrease in size while the application runs.(The heap is not same a heap(tree). )

 </br>

![image](https://github.com/mingzheruan/Notebook/blob/master/Algorithm%20--%20laioffer/Image/Elementary%20Class01.png)

   </br>

### Review: Class / Object / Reference / Dereference

#### Stack + Heap

1. Stack + Heap are memory (RAM) segments.

2. RAM: Random Access Memory.

3. Difference
   1. Space: stack ~ MB, heap ~ GB
   2. Read/Write speed: stack(1 CPU instruction) >>> heap("bookkeeping")
4. Stack frame
   1. 1 function invocation -> 1 stack frame "pushed" onto the call stack (a pile of books)
   2. if a function is never called, its stack frame is never created.

 </br>

#### Java Data Type

1. Primitive types: data directly stored in **memory**(no reference)
   1. Numeric
      1. Integer
         + byte short int long
      2. Decimal
         + float, double
   2. Character
      
      + char
   3. Boolean
      
      + boolean
      
       </br>
2. Reference types: objects stored in heap(operated by references)
   1. class
   2. Interface
   3. Enum

 </br>

+ Serves as object states (fields) - heap
+ Serves as temporary variables in our methods (local variables) - stack



 </br>



### Variable Scope

1. Scope: **lifetime and accessibility/visibility** of a variable. ~ How large the scope depends on where a variable is declared.
2. Simply, the scope is the **innermost{}** wrapping up the **declaration**.
3. Local (local to function) variables: the variables whose lifetime is strictly tied with a function. 

 </br>

 ### Variables and their scopes

#### Local variables

+ Local variables must be initizlized before use.

+ One local variable has the lifetime of their own scope.

 </br>

#### Instance variable(field)

instance field == instance variable == member variable

 </br>

**Non-static** variables defined **within a class**, but not within any methods.

Instance variables have the same life cycle as the instance.

Instance variables' vasibility is defined by their access modifiers.

 </br>

![image](https://github.com/mingzheruan/Notebook/blob/master/Algorithm%20--%20laioffer/Image/Elementary%20Class02.png)

 </br>

##### Class variables (static)

similar to instance variables, just belong to class but not an instance

 </br>

#### Static 

+ static method can(directly) access only static variables/method
+ Non-static method can access both static and non-static variables/methods

 </br>

### Stack and Heap Comparison

+ **Local type cariables are always on stack.**
+ **Whenever an object is created, its content(i.e, instance variable) is always stored in the Heap space.**
+ Stack variable is destroyed after out of its scope.
+ Heap variable is destroyed by **garbage collector(GC)**

 </br>

#### Errors:

+ **NullPointerException:** happens when we try to dereference a reference with null value
+ **ArrayIndexOutOfBoundException:** if the index specified is not in the valid range of the array.

<br>

### ArrayList

+ ArrayList is regard as a **resizable** array

<br>

### Recursion, Queue, Stack

#### Recursion

1. function calls itself

2. Boil down a big problem to smaller ones(size n depends on size n-1, or n-2 or ...n/2)

3. Implementation:

   1. **Base case:** smallest problem to solve
   2. **Recursion rule:** how to make the problem smaller(if we can resolve the same problem but with a smaller size, then what is left to do for the current problem size n)

   <br>

####  (three steps methods)

1. **Define subproblem**
2. **find recursion rule**
3. **define base case**

<br>

```java
Example 1: Fibonacci sequence:

  f(n)
  0  1  2  3  4  5  6  7  8
  0  1  1  2  3  4  8  13  21...
                          a b
  
  
  f(n)
    - subproblem: f(n-1), f(n-2)
    - recursion rule: f(n) = f(n - 1) + f(n - 2)
    - base case: f(0) = 0, f(1) = 1
      
      
      
      
      
    public int fib(int n){
      
        //base case
        if (n == 0) {
            return 0;
        } else if (n == 1){
            return 1;
        } else {
        //recursion rule
            return fib(n - 1) + fib(n - 2);
        }
    }

```

<br>

**Height of the tree is n,      2^0 + 2^1 + 2^2 + ... + 2^(n - 1) = 2^n**

Reason:

+  each nodes represents a single function call
+  each function call's time complexity is O(1)

<br>

Total nodes in the recursion tree = 2^n

And the time complexity in each node is O(1)

Thus, total time complexity = O(2^n)

<br>

Space = O(n)  (call stack)

<br>

**Each node/edge in the recursion tree represents a recursive function call.**

**-Going down:** make a new recursive call, breaking point at previous level

**-Going up:** all the branches are finished (all the subtree finished), return to the previous level.



<br>

<br>

```java
Example 2: Power
  a ^ b (a > 0, b >= 0)
  2 ^ 3 = 8
  4 ^ 2 = 16
  
  problem: f(a, b)
    
  Method 1
  f(a, b)
    - subproblem: f(a, b - 1),
		- recursion rule: f(a, b) = a * f(a, b - 1)
    - base case: f(a, 0) = 1
      
  Method 2
  f(a, b)
    - subproblem: f(a, b / 2),
    - recursion rule: 
				- b is even: f(a, b) = f(a, b / 2) ^ 2
        - b is odd: f(a, b) = f(a, b / 2) ^ 2 * a
    - base case: f(a, 0) = 1
      
  Method 3
  f(a, b)
    - subproblem: f(a, b / 3)
    - recursion rule:
				- 3 conditions
    - base case: f(a, 0) = 1
       
```

<br>

**Note some key points:**

1. Each function call is **individual**, if you write a statement of a function call, it will follow and execute all the statements defined in the function until finish them all.
2. The program will only run as what you told them to do
   1. If there is a function call, it will follow the procedure until it finishes all the statement.
   2. **It won't by default cache any result of previous computation unless you do it explicitly.**
3. The benefit of **recursion tree**
   1. Help you understand how actually the program runs
   2. Perform correctly the complexity analysis

<br>

+  **# of branches = # of usage of subproblems = # of recursive calls**

![image](https://github.com/mingzheruan/Notebook/blob/master/Algorithm%20--%20laioffer/Image/Elementary%20Class03.png)

<br>

#### Queue and Stack (API)

1. **Queue**

   + **Create an empty queue:**

     Queue<Integer> queue = new LinkedList<>();

   + **Add an element:**

     queue.offer(1);

     queue.offer(2);      // [1, 2]

   + **Remove an element from the front:**

     queue.poll();          //[2]

   + **Take a look at the front element:**

     int frontElement = queue.peek();

   + **Get the size of the queue:**

     int queueSize = queue.size();

   + **Determine whether the queue is empty:**

     boolean isEmptyQueue = queue.isEmpty();



<br>

2. **Stack**

   + **Create an empty stack:**

     Deque<Integer> stack =  new LinkedList<>();

   + **add an element:**

     stack.push(1);

     stack.push(2);   //  top: [2, 1]

   + **Remove an element from the top:**

     stack.pop();

   + **Take a look at the top element:**

     int topElement = stack.peek();

   + **Get the size of the stack:**

     int stackSize = stack.size();

   + **Determine whether the stack is empty:**

     boolean isEmptyStack = stack.isEmpty();

<br>

### Binary Search

#### Principles of Binary Search

1. we must guarantee that the search space decrease over time(after each iteration)
2. we must guarantee that the target (if exists) cannot be ruled out accidentally, when we change the value of left or right. (It is critical to define the rule about how to move the ranger search)

<br>

1. what does left, right mean?
   - **Searching range: we guarantee the final answer is in [left, right] all the time**
2. what does while loop do?
   + **Using mid element to determine and guarantee next round, point 1 holds true**
3. when should the while loop terminate(base case)?
   + **it must be able to terminate, there should not be any infinite loop**
   + **depends on how you define the recursive rule**

<br>

```
Example 1: First Occurrence

Given a target integer T and an integer array A sorted in ascending order, find the index of the first occurrence of T in A or return -1 if there is no such index.

Assumptions

There can be duplicate elements in the array.
Examples

A = {1, 2, 3}, T = 2, return 1
A = {1, 2, 3}, T = 4, return -1
A = {1, 2, 2, 2, 3}, T = 2, return 1
Corner Cases

What if A is null or A of zero length? We should return -1 in this case.





public class FirstOccurrence {
	public int fisrtOccur(int[] array, int target) {
		if (array == null || array.length == 0) {
			return -1;	
		}
		
		int left = 0;
		int right = array.length - 1;
		
		// we need to use left < right - 1 here to make sure there is no infinite loop.
		// Think about the case when left == right - 1,
		// then mid == left, it will be possible picking [mid, right] for the next round
		// and it will go into an infinite loop in that case.
		
		while (left < right - 1) {
			int mid = left + (right - left) / 2;
			
			if (array[mid] < target) {
				left = mid;
			} else {
				right = mid;
			}
		}
		
		// Make sure you understand all the possible situations when entering
		// this postprocessing procedure.
		// 1. array has only 1 element.
		// 2. array has only 2 element.
		// 3. left == right - 1 and left is the result.
		// 4. left == right - 1 and right is the result.
		// 5. left == right - 1 and none of left, right is the result.
		
		if (array[left] == target) {
			return left;
		} 
		if (array[right] == target){
			return right;
		}
		return -1;
	}
}



```

<br>

```java
Example 2 : Search In Sorted Matrix I
  
Given a 2D matrix that contains integers only, which each row is sorted in an ascending order. The first element of next row is larger than (or equal to) the last element of previous row.

Given a target number, returning the position that the target locates within the matrix. If the target number does not exist in the matrix, return {-1, -1}.

Assumptions:

The given matrix is not null, and has size of N * M, where N >= 0 and M >= 0.
Examples:

matrix = { {1, 2, 3}, {4, 5, 7}, {8, 9, 10} }

target = 7, return {1, 2}

target = 6, return {-1, -1} to represent the target number does not exist in the matrix.
  
  
  
 public class SearchInSortedMatrixI {
   // Assumptions: matrix is not null, and hase size N * M where N >= 0 and M >= 0.
   // return {-1, -1} if not found
   
   // Method 1 (not reconmmended): find row first then find col
   
   public int[] searchI (int[][] matrix, int target) {
                                                      
     int[] result = new int[] {-1, -1};
     if (matrix.length == 0 || matrix[0].length == 0) {
       return result;
     }
     
     // Find the possible row location for target.
     int row = findRow(matrix, 0, matrix.length - 1, target);
     if (row == -1) {
       return result;
     }
     
     // Find the possible col location in the row for target
     int col = findCol(matrix[row], 0, matrix[row].length - 1, target);
     if (col == -1) {
       return result;
     }
     result[0] = row;
     result[1] = col;                                                 
     return result;                                                 
   }
   
   // Find the largest row with first element <= target
   private int findBow(int[][] matrix, int up, int down, int target) {
     while (up <= down) {
       int mid = up + (down - up) / 2;
       if (matrix[mid][0] > target) {
         down = mid - 1;
       } else {
         up = mid + 1;
       }
     }
     return down;
   }
   
   // Classical binary search to find the col on the row.
   private int findCol(int[] array, int left, int right, int target) {
     while (left <= right) {
       int mid = left +(right - left) / 2;
       if (array[mid] == target) {
         return mid;
       } else if (array[mid] < target) {
         left = mid + 1;
       } else {
         right = mid - 1;
       }
     }
     return -1;
 }
  
  
  
   
   // Method 2 (better): covert the 2D array to 1D array and do binary search.
   
   public int[] search(int[][] matrix, int target) {
     
     if (matrix.length == 0 || matrix[0].length == 0) {
       return new int[] {-1, -1};
     }
     
     int rows = matrix.length;
     int cols = matrix[0].length;
     int left = 0;
     
     // covert the 2D array to 1D array with rows * cols elements.
     
     int right = rows * cols - 1;
     while (left <= right) {
       int mid = left + (right - left) / 2;
       
       // convert the position in 1D array back to row and col in 2d array.
       int row = mid / cols;
       int col = mid % cols;
       if (matrix[row][cols] == target) {
         return new int[] {row, col};
       } else if (matrix[row][col] < target) {
         left = mid + 1;
       } else {
         right = mid - 1; 
       }
     }
     return new int[] {-1, -1};
   }
```





### LinkList







讲题的时候，从high level 说，

之后说细节

