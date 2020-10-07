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

  </br>

#### Operators and Precedence

+ bitwise AND ---- & 

+ bitwise inclusive ---- |	     		

  Example: 

  if( foo() & goo() ) ---- two function both run.

  if( foo() | goo() ) ---- two function both run.

 </br>

+ logical AND ---- &&

+ logical OR ---- ||

  Example:

  if( foo() && goo() ) ---- if foo() is false, the judgement is over. no run goo()

  if( foo() || goo() ) ---- if foo() is true, the judgement is over. no run goo()

 </br>

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

**Non-static** variables defined **within a class**, but not within any methods.

Instance variables have the same life cycle as the instance.

Instance variables' vasibility is defined by their access modifiers.

 </br>

![alt 2](/Users/ruanmingzhe/Documents/GitHub/Notebook/Algorithm -- laioffer/Image/Elementary Class02.png)

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
+ 