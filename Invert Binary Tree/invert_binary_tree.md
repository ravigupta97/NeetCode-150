
## 🧠 Problem: Invert Binary Tree (LeetCode #226)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/invert-binary-tree/description/](https://leetcode.com/problems/invert-binary-tree/description/)


### ❓ Problem Statement:
Given the root of a binary tree, invert the tree, and return its root.

Example 1:

![image](https://github.com/user-attachments/assets/48f2cfc2-1dde-4ec3-890f-0990cbbac655)

- Input: root = [4,2,7,1,3,6,9]
- Output: [4,7,2,9,6,3,1]

Example 2:

![image](https://github.com/user-attachments/assets/90ff1545-1ca0-4efa-9c3a-89a1dcba2999)

- Input: root = [2,1,3]
- Output: [2,3,1]

Example 3:

- Input: root = []
- Output: []

Constraints:

- The number of nodes in the tree is in the range [0, 100].
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
    def invertTree(self, root: Optional[TreeNode]) -> Optional[TreeNode]:
        # Base Case
        if not root:
            return root
        # Call Left SubTree
        self.invertTree(root.left)
        # Call Right SubTree
        self.invertTree(root.right)

        # Swap the nodes
        root.left, root.right = root.right, root.left

        # Return root
        return root  
```

---

### 🧠 Explanation:

- Use Post Order Traversal of tree
- Call Left SubTree
- Call Right SubTree
- To invert the tree Swap both the nodes and return the tree

---

⏱️ Time Complexity:

- Time : O(n)
- Space : O(n) recursive stack space
