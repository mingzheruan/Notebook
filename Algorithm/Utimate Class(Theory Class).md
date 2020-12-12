# Utimate Class (Theory Class)

## Class2 Recursion I && Sorting Algorithms

Recursion

1.  表象上: function calls itself
2.  实质上: Boil down a big problem to smaller ones (size n depends on size n-1, or n-2 or...n/2)
3.  Implementation 上:
    1.  Base case: smallest problem to solve
    2.  Recursive rule: how to make the problem smaller (if we can resolve the same problem but with a smaller size, then what is left to do for the current problem size n)

## Class4 Queue & Stack

## Class10 Bit Representation & bit Operations

### Decimal representation

2084 = 2 * 10^3 + 0 * 10^2 + 8 * 10^1 + 4 * 10^0

逢十进一

### Binary representation

5 = 1 * 2^2 + 0 * 2^1 + 1 * 2^0 = 0b101

对于负数 "-1": 1变反加1，

1     ==	0000 0000 0000 0000 0000 0000 0000 0000

-1 变反   1111 1111 1111 1111 1111 1111 1111 1110

​    加一   1111 1111 1111 1111 1111 1111 1111 1111



### Bit Operation

1.  &    bitwise AND (ampersand)   **if (true1 && true2)**
    1.  bitwise and (for each bit)
    2.  Difference: && uses short-circuit evaluation
2.  |    OR  **if (true1 || true2)**
3.  ~    NOT (1->0 and 0->1 for each bit) a = 5; b = ~a; tilde
    1.  a = 5 =   0b0000 0101
    2.  b = ~a = 0b1111 1010
    3.  -1 == (~a)+1 if a>= 0
4.  ^    XOR
    1.  00 -> 0
    2.  11 -> 0
    3.  01 or 10 -> 1
5.  **<<**  left shift  右侧补充零
6.  **>>**  right shift 左侧补充原先的符号位





### Building Blocks

1.Bit tester: Given a number x, test whether x's k-th bit is one

x      	         = 0b b7 b6 b5 b4 b3 b2 b1 b0

x >> k          = 0b b7 b7 b7 b7 b6 b5 b4 b3 

1                  = 0b  0   0    0   0   0   0   0   1

(x >> k) & 1  = 0b  0   0    0   0   0   0   0   b3

