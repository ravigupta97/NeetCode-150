
## 🧠 Problem: Two Sum (LeetCode #1)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/two-sum](https://leetcode.com/problems/two-sum)


### ❓ Problem Statement:
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

 

Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
Example 2:

Input: nums = [3,2,4], target = 6
Output: [1,2]
Example 3:

Input: nums = [3,3], target = 6
Output: [0,1]
 

Constraints:

- 2 <= nums.length <= 104
- -109 <= nums[i] <= 109
- -109 <= target <= 109
- Only one valid answer exists.
 

Follow-up: Can you come up with an algorithm that is less than O(n2) time complexity?


---

### ✅ Solution (Python):
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        #Dictionary to store elements and their indices
        num_indices = {}
        for i, num in enumerate(nums):
            complement = target - num
            # check if complement exists in the dictionary
            if complement in num_indices:
                # if it does, return the indices of
                #current element and its complement
                return [num_indices[complement], i]
            #if the complement does't exist add it to the dictionary
            num_indices[num] = i
        # if no solution found return empty list 
        return []
```

---

### 🧠 Explanation:

- Use Dictionary to store elements and their indices
- Check if the complement exists in the dictionary or not
- If it does exist then return the indices of current and complement element

---

⏱️ Time Complexity:

- Time : O(n)
- Space : O(n)
