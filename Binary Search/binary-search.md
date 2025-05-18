
## 🧠 Problem: Binary Search (LeetCode #704)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/binary-search/](https://leetcode.com/problems/binary-search/)


### ❓ Problem Statement:
Given an array of integers nums which is sorted in ascending order, and an integer target, write a function to search target in nums. If target exists, then return its index. Otherwise, return -1.

You must write an algorithm with O(log n) runtime complexity.

 

Example 1:

- Input: nums = [-1,0,3,5,9,12], target = 9
- Output: 4
- Explanation: 9 exists in nums and its index is 4

Example 2:

- Input: nums = [-1,0,3,5,9,12], target = 2
- Output: -1
- Explanation: 2 does not exist in nums so return -1
 
Constraints:

- 1 <= nums.length <= 104
- -104 < nums[i], target < 104
- All the integers in nums are unique.
- nums is sorted in ascending order.

---

### ✅ Solution (Python):
```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        # Initialize the start and end of the list
        start = 0
        end = len(nums)-1
        
        # Traverse over the list till start is less than end
        while start <= end:
            # Caluclate the mid of the list using start and end
            mid = start + (end-start)//2
            # If target is at the mid return mid as index
            if target == nums[mid]:
                return mid
            # If target is greater than value at mid move the start to mid+1
            elif target > nums[mid]:
                start = mid + 1
            # If target is smaller than value at mid move the end to mid-1
            elif target < nums[mid]:
                end = mid-1
        
        return -1
```

---

### 🧠 Explanation:

- Initialize the start and end of the list
- Traverse over the list till start is less than end
- Caluclate the mid of the list using start and end
- If target is at the mid return mid as index
- If target is greater than value at mid move the start to mid+1
- If target is smaller than value at mid move the end to mid-1

---

### ⏱️ Time Complexity:

- Time : O(n log n)
