
## 🧠 Problem: Symmetric Tree (LeetCode #101)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/symmetric-tree/](https://leetcode.com/problems/symmetric-tree/)


### ❓ Problem Statement:
Given the root of a binary tree, check whether it is a mirror of itself (i.e., symmetric around its center).


Example 1:

![image](https://github.com/user-attachments/assets/955b4fe6-c6bb-4932-b498-12d61e91b9ef)

- Input: root = [1,2,2,3,4,4,3]
- Output: true

Example 2:

![image](https://github.com/user-attachments/assets/2df0d296-d249-46d2-87fb-adfad5262c48)

- Input: root = [1,2,2,null,3,null,3]
- Output: false
 
Constraints:

- The number of nodes in the tree is in the range [1, 1000].
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
    def isSymmetric(self, root: Optional[TreeNode]) -> bool:
        # base case
        if not root:
            return False
        
        # Call the isSame method recursively
        return self.isSame(root.left, root.right)

    # Method to check if the left subtree is a mirror reflection of right subtree
    def isSame(self, leftRoot: Optional[TreeNode], rightRoot: Optional[TreeNode]) -> bool:
        # Check if both root nodes are null then return True
        if leftRoot == None and rightRoot == None:
            return True
        
        # Check if exactly one of them is null then return False
        if leftRoot == None or rightRoot == None:
            return False
        
        # Check if root node's value are not same then return False
        if leftRoot.val != rightRoot.val:
            return False
        
        # Return True if root node's values are same and left and right subTrees are symetric
        return self.isSame(leftRoot.left, rightRoot.right) and self.isSame(leftRoot.right, rightRoot.left)

```

---

### 🧠 Explanation:

- Create a method to check if the left subtree is a mirror reflection of right subtree
- Check if both root nodes are null then return True
- Check if exactly one of them is null then return False
- Check if root node's value are not same then return False
- Return True if root node's values are same and left and right subTrees are symetric
- Call the isSame method recursively in the isSymmetric method


---

### ⏱️ Time Complexity:

- Time : O(n)
