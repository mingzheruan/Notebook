### Primitive Types and Basic Operations

#### Primitive Types

byte -- short -- int -- long -- float -- double -- char -- boolean

byte -> short -> int -> long -> float -> double

------------------------------------------------------------>

​									Widening (精度)

it is okay to cast lower precision type to higher precision type implicitly. 

not from high precision type to lower precision type. Java will always help you to perform casting to higher precision if needed

```diff
 if you are not sure, always use explicit conversion!!!
```



#### Operators and Precedence

+ bitwise AND ---- & 

+ bitwise inclusive ---- |	     		

  Example: 

  if( foo() & goo() ) ---- two function both run.

  if( foo() | goo() ) ---- two function both run.



+ logical AND ---- &&

+ logical OR ---- ||

  Example:

  if( foo() && goo() ) ---- if foo() is false, the judgement is over. no run goo()

  if( foo() || goo() ) ---- if foo() is true, the judgement is over. no run goo()



### Array, Class and Objects

+ You must specify the length of the array.

+ List, ArrayList, LinkedList are different to arrays!

  ```  
  The length cannot be changed after creation
  ```



+ Declaration: associate a variable name with an object type

```java
Student firstStudent
```



+ Instantiation: the new keyword is a java operator that creates the object

```\java
firstStudent = new student

//create an object in the memory and return its refernece to firstStudent
```



+ Initialization: the new operator is followed by a call to a constructor, which initializes the new object



### Object Memory Layout

#### Memory spaces in a java program: Stack and Heap

+ Stack: In computer science, a call stack is a stack data structure that stores information about the active subroutines of a computer program(stack frame). This kind of stack is also known as an execution stack, program stack, ccontrol stack, run-time stack, or machine stack, and is often shortened to just "the stack" 



+ Heap: Java objects reside in an area called the heap. The heap is created when the JVM starts up and may increase or decrease in size while the application runs.(The heap is not same a heap(tree). )



![alt Elementary Class01](/Users/ruanmingzhe/Documents/GitHub/Notebook/Algorithm -- laioffer/Image/Elementary Class01.png)



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



#### Java Data Type

1. Primitive types: data directly stored in memory(no reference)
   1. Numeric
      1. Integer
         + byte short int long
      2. Decimal
         + float, double
   2. Character
      + char
   3. Boolean
      + boolean
2. Reference types: objects stored in heap(operated by references)
   1. class
   2. Interface
   3. Enum



+ Serves as object states (fields) - heap
+ Serves as temporary variables in our methods (local variables) - stack



### Variable Scope

1. Scope: **lifetime and accessibility/visibility** of a variable