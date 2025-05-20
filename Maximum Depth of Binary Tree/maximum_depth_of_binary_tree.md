
## 🧠 Problem: Maximum Depth of Binary Tree (LeetCode #104)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/maximum-depth-of-binary-tree/description/](https://leetcode.com/problems/maximum-depth-of-binary-tree/description/)


### ❓ Problem Statement:
Given the root of a binary tree, return its maximum depth.

A binary tree's maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.

 
Example 1:

![image](https://github.com/user-attachments/assets/a52dab1e-5ad7-4a29-9f0b-b807425d3c5f)

- Input: root = [3,9,20,null,null,15,7]
- Output: 3

Example 2:

- Input: root = [1,null,2]
- Output: 2
 

Constraints:

- The number of nodes in the tree is in the range [0, 104].
- -100 <= Node.val <= 100
  
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
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        if root:
            return max(self.maxDepth(root.left), self.maxDepth(root.right)) + 1
        else:
            return 0
```

---

### 🧠 Explanation:

- Use Recursion to traverse the tree
- At each node, calculate the depth of the left and right subtree, and take the maximum of the two, then add 1 for the current node

---

### ⏱️ Time Complexity:

- Time : O(n) we visit each node once
- Space : O(h) due to recursion stack, where h is the height of the tree
