## Tree Traversal #

### Inorder Traversal ###

Visit the left, root, right

### Java Application ###

```
  void inorder(TreeNode root) {
      if (root == null) {
        return;
      }
      inorder(root.left); 
      System.out.print(root.val + " ");
      inorder(root.right);
  }
```  

### Preorder Traversal ###

Visit the root, left, right

```
  void preorder(TreeNode root) {
    if (root == null) {
      return;
    }
    System.out.println(root.val + " ");
    preorder(root.left);
    preorder(root.right);
  }
```

### Postorder Traversal ###

Visit the left, right, root 

```
  void postorder(TreeNode root) {
    if (root == null) {
      return;
    }
    postorder(root.left);
    postorder(root.right);
    System.out.println(root.val + " ");
  }
```
