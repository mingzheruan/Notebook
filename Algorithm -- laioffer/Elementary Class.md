### Primitive Types and Basic Operations

#### Primitive Types

byte -- short -- int -- long -- float -- double -- char -- boolean

byte -> short -> int -> long -> float -> double

------------------------------------------------------------>

​									Widening (精度)

it is okay to cast lower precision type to higher precision type implicitly. 

not from high precision type to lower precision type. Java will always help you to perform casting to higher precision if needed

```diff
 if you are not sure, always use explicit conversion
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



