
## 🧠 Problem: Diameter of Binary Tree (LeetCode #543)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/diameter-of-binary-tree/description/](https://leetcode.com/problems/diameter-of-binary-tree/description/)


### ❓ Problem Statement:
Given the root of a binary tree, return the length of the diameter of the tree.

The diameter of a binary tree is the length of the longest path between any two nodes in a tree. This path may or may not pass through the root.

The length of a path between two nodes is represented by the number of edges between them.

 

Example 1:

![image](https://github.com/user-attachments/assets/927e178f-da0f-4d1a-8244-19d2d19b9d65)

- Input: root = [1,2,3,4,5]
- Output: 3
- Explanation: 3 is the length of the path [4,2,1,3] or [5,2,1,3].

Example 2:

- Input: root = [1,2]
- Output: 1
 

Constraints:

- The number of nodes in the tree is in the range [1, 104].
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
    def diameterOfBinaryTree(self, root: Optional[TreeNode]) -> int:
        self.max_diameter = 0

        def dfs(root):
            if not root:
                return 0
            
            left_height = dfs(root.left)
            right_height = dfs(root.right)

            self.max_diameter = max(self.max_diameter, left_height+right_height)

            return 1 + max(left_height, right_height)

        dfs(root)

        return self.max_diameter
```

---

### 🧠 Explanation:

- Initialize a variable to store the maximum diameter
- Create a method to calculate depth of binary tree using recursion and check the base case
- Calculate the left height and right height of subtree using recursion
- max_diameter is updated to the max of its current value and diameter of current node
- The method returns the depth of subtrees including the node.
- Call the method dfs and return the max_diameter variable

---

### ⏱️ Time Complexity:

- Time : O(n)
- Space : O(n)
