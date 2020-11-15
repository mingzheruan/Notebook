# Utimate Class ( Aha moment)

# Class1

Student firstStudent = new Student("Tom");    

"firstStudent" is an reference. "new Student" is instantiation and it stored in heap. 

<br>

![Image](https://github.com/mingzheruan/Notebook/blob/master/Algorithm%20--%20laioffer/Image(Utimate%20Class)/UtimateClass01.png)

<br>

Object 上所有的field 都在heap上，field又指向同在field上的数据

<br>

where to store local variables:

+ primative: stack
+ **object: its reference stores in stack, the object self stores in heap.**

<br>

where to store fields:

+ primitive: heap
+ object: heap (**its reference stores in heap as well!!!**)



## Class2 Recursion I && Sorting Algorithms

Recursion

1.  表象上: function calls itself
2.  实质上: Boil down a big problem to smaller ones (size n depends on size n-1, or n-2 or...n/2)
3.  Implementation 上:
    1.  Base case: smallest problem to solve
    2.  Recursive rule: how to make the problem smaller (if we can resolve the same problem but with a smaller size, then what is left to do for the current problem size n)

## Class3



