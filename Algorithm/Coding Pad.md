# Coding Pad

```JAVA
public TreeNode search(TreeNode root, int target) {
    while (root != null && root.key != target) {
        if (target < root.key) {
            root = root.left;
        } else {
            root = root.right;
        }
    }
    return root;
}

```

