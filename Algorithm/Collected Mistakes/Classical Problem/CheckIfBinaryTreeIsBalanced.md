# CheckIfBinaryTreeIsBalanced

```java
/*
Check if a given binary tree is balanced. A balanced binary tree is one in which the depths of every node’s left and right subtree differ by at most 1.

Examples

        5

      /    \

    3        8

  /   \        \

1      4        11

is balanced binary tree,

        5

      /

    3

  /   \

1      4

is not balanced binary tree.

Corner Cases

What if the binary tree is null? Return true in this case.
How is the binary tree represented?

We use the level order traversal sequence with a special symbol "#" denoting the null node.

For Example:

The sequence [1, 2, 3, #, #, 4] represents the following binary tree:

    1

  /   \

 2     3

      /

    4
*/
Method 1 
   public boolean isBalanced(TreeNode root) {
    // sanity check
    if (root == null) {
      return true;
    }
	int leftHeight = findHeight(root.left);
    int rightHeight = findHeight(root.right);
    if (Math.abs(leftHeight - rightHeight) > 1) {
      return false;
    }
    return isBalanced(root.left) && isBalanced(root.right);
  }
  
  private int findHeight(TreeNode root) {
    if (root == null) {
      return 0;
    }
    return Math.max(findHeight(root.left), findHeight(root.right)) + 1;
  }

Method 2 (better TC: O(n))
 public boolean isBalanced(TreeNode root) {
    // sanity check
    if (root == null) {
      return true;
    }

    return height(root) != -1;
  }
  
  private int height(TreeNode root) {
    if (root == null) {
      return 0;
    }

    int leftHeight = height(root.left);
    if (leftHeight == -1) {
      return -1;
    }

    int rightHeight = height(root.right);
    if (rightHeight == -1) {
      return -1;
    }

    if (Math.abs(leftHeight - rightHeight) > 1) {
      return -1;
    }

    return Math.max(leftHeight, rightHeight) + 1;
  }
```

## Method 1 vs Method 2 

方法二好在哪里：

```java
Method1: recursion tree
                             IsBalanced(root: n nodes)
                       getHeight(C1)                 getHeight(C2)
                           n/2             +              n/2
                            Time spent in this node = O(n)                           = n
                         /                                   \
                      
       IsBalanced(C1: n/2 nodes)                  IsBalanced(C2: n/2 nodes)
     getHeight(C11)     getHeight(C12)          getHeight(C21)     getHeight(C22)
          n/4      +       n/4                       n/4      +       n/4                               
      Time spent in this node = O(n/2)          Time spent in this node = O(n/2)     = n
      /                           \                 /                           \
IsBalanced(C11)             IsBalanced(C12)   IsBalanced(C11)     IsBalanced(C12)    = n
  n/8 + n/8                    n/8 + n/8        n/8 + n/8             n/8 + n/8
    O(n/4)                       O(n/4)           O(n/4)                O(n/4)       = n
    /   \                          / \              /  \                 /  \
    ...........
    
Tree 的时间复杂度一般是： O(所有节点个数 * 单个节点所用的时间复杂度)
Tree
```



