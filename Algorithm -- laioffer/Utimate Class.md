# Utimate Class (Practice Class - Aha moment)

# Class1

Student firstStudent = new Student("Tom");    

"firstStudent" is an reference. "new Student" is instantiation and it stored in heap. 

<br>

![Image](https://github.com/mingzheruan/Notebook/blob/master/Algorithm%20--%20laioffer/Image(Utimate%20Class)/UtimateClass01.png)

<br>

where to store local variables:

+ primative: stack
+ **object: its reference stores in stack, the object self stores in heap.**

<br>

where to store fields:

+ primitive: heap
+ object: heap (**its reference stores in heap as well!!!**)