

## 🧠 Problem: Validate Binary Tree (LeetCode #98)
**Difficulty:** Medium  
**Link:** [https://leetcode.com/problems/validate-binary-search-tree/description/](https://leetcode.com/problems/validate-binary-search-tree/description/)


### ❓ Problem Statement:
Given the root of a binary tree, determine if it is a valid binary search tree (BST).

A valid BST is defined as follows:

The left subtree of a node contains only nodes with keys less than the node's key.
The right subtree of a node contains only nodes with keys greater than the node's key.
Both the left and right subtrees must also be binary search trees.
 

Example 1:

![image](https://github.com/user-attachments/assets/a909b08d-5bf4-48d6-b3eb-05f154391d50)


- Input: root = [2,1,3]
- Output: true

Example 2:

![image](https://github.com/user-attachments/assets/5d2bcd61-b145-4b91-aa1e-ed1a51523d91)


- Input: root = [5,1,4,null,null,3,6]
- Output: false
- Explanation: The root node's value is 5 but its right child's value is 4.
 

Constraints:

- The number of nodes in the tree is in the range [1, 104].
- -231 <= Node.val <= 231 - 1

---

### ✅ Solution (Python):
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def isValidBST(self, root: Optional[TreeNode]) -> bool:
        def dfs(node, min_val, max_val):
            if not node:
                return True
            if not (min_val < node.val < max_val):
                return False

            return (dfs(node.left, min_val, node.val) and dfs(node.right, node.val, max_val))

        return dfs(root, float('-inf'), float('inf')) 
        
```

---

### 🧠 Explanation:

- Create a helper function dfs to traverse over the tree recursively.
- Check the base case if the node is valid.
- Check if the current node value is within the valid range, if not its not a BST.
- For left child, update max_val to current node's value.
- For right child, update min_val to current node's value.

---

### ⏱️ Time Complexity:

- Time : O(n)
- Space : O(h), h is the height of the tree
