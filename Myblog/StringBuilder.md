### StringBuilder's API (Common)

-   append()
    -   append(char ch): check capacity of StringBuilder and expand if necessary - amortized O(1)
    -   append(String s): check capacity of StringBuilder and expand if necessary - amortized O(s.length())
-   insert(int index, char ch):  O(n)
-   delete(int start, int  end):  O(n)
-   deleteCharAt(int index): O(n) - delete at tail - O(1)
-   
-   reverse()
-   replace(int start, int end, String str)
-   setLength()
-   [more detail](https://docs.oracle.com/javase/7/docs/api/java/lang/StringBuilder.html)

