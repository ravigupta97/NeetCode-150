
## 🧠 Problem: Convert Sorted Array to Binary Search Tree (LeetCode #108)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/](https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/)


### ❓ Problem Statement:
Given an integer array nums where the elements are sorted in ascending order, convert it to a height-balanced binary search tree.

 

Example 1:

![image](https://github.com/user-attachments/assets/cfef22c5-8e7c-458c-ae93-aa236be6ba24)

- Input: nums = [-10,-3,0,5,9]
- Output: [0,-3,9,-10,null,5]
- Explanation: [0,-10,5,null,-3,null,9] is also accepted:

![image](https://github.com/user-attachments/assets/12bb2e2c-8a42-4b7f-ac17-1f2165830dc1)

Example 2:

![image](https://github.com/user-attachments/assets/71db0910-0a13-442a-8b13-0d78a39599a7)

- Input: nums = [1,3]
- Output: [3,1]
- Explanation: [1,null,3] and [3,1] are both height-balanced BSTs.
 

Constraints:

- 1 <= nums.length <= 104
- -104 <= nums[i] <= 104
- nums is sorted in a strictly increasing order.

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
    def sortedArrayToBST(self, nums: List[int]) -> Optional[TreeNode]:
        if not nums:
            return None
        
        mid = len(nums)//2
        root = TreeNode(nums[mid])
        root.left = self.sortedArrayToBST(nums[:mid])
        root.right = self.sortedArrayToBST(nums[mid+1:])

        return root
```

---

### 🧠 Explanation:

- Calculate the mid of the array as it will be the root node of the new tree
- Create a new tree and assign the root as the mid of the array
- Recursively apply the same approach to the left and right halves of the array
- Attach the calculated left and right node to the root of the tree
- Return the root of the tree

---

### ⏱️ Time Complexity:

- Time : O(n)
- Space : O(n)
