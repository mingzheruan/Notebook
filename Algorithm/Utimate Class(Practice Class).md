# Utimate Class ( Aha moment)

## Class1 Classes, objects, and reference I

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

    <br>

**Java pass by value(copy), not by reference**

+   primitive type: copy of the value itself

+   object: copy of the object reference



## Class2 Classes, objects, and references - II

## static : 

Members (fields, methods, classes) belong to class, not object(instance)【一旦使用static，这个就是此class的共有属性，不在属于单个实例】

<br>

## Final:

Constants: "Once assigned, cannot be changed." 

Final class: A class that cannot be derived.

Final method: A method that cannot be overridden.（无法重写）

Final variable: A variable that once assigned, cannot be assigned again.

<br>

## object

+   the elements in the array still occupy consecutive memory space on the heap
+   "length" is a field of the array object
+   **array length cannot be changed after the array object is created. (final)**

## Class3 Practice Problems



## Class4

LinkedList 不能失去对头的控制

快慢指针， N3更好（偶数）， 当将链表拆分为2半的时候，方便断开





