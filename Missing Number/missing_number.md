
## 🧠 Problem: Missing Number (LeetCode #268)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/missing-number/](https://leetcode.com/problems/missing-number/)


### ❓ Problem Statement:
Given an array nums containing n distinct numbers in the range [0, n], return the only number in the range that is missing from the array.

 
Example 1:

- Input: nums = [3,0,1]
- Output: 2

Explanation:
- n = 3 since there are 3 numbers, so all numbers are in the range [0,3]. 2 is the missing number in the range since it does not appear in nums.

Example 2:

- Input: nums = [0,1]
- Output: 2

Explanation:
- n = 2 since there are 2 numbers, so all numbers are in the range [0,2]. 2 is the missing number in the range since it does not appear in nums.

Example 3:

- Input: nums = [9,6,4,2,3,5,7,0,1]
- Output: 8

Explanation:
- n = 9 since there are 9 numbers, so all numbers are in the range [0,9]. 8 is the missing number in the range since it does not appear in nums.

Constraints:

- n == nums.length
- 1 <= n <= 104
- 0 <= nums[i] <= n
- All the numbers of nums are unique.
 
Follow up: Could you implement a solution using only O(1) extra space complexity and O(n) runtime complexity?

---

### ✅ Solution (Sum of All Elements) (Python):
```python
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        n = len(nums)
        actual_sum = 0
        expected_sum = n*(n+1)//2

        for num in nums:
            actual_sum += num
        
        return expected_sum - actual_sum

```

---

### 🧠 Explanation:

- Calculate sum of elements in range [0,n]
- Calculate sum of the list nums
- missing number will be subtraction of both

---

### ⏱️ Time Complexity:

- Time : O(n)
- Space : O(1)

---

### ✅ Solution (Using XOR) (Python):
```python
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        n = len(nums)
        ans = 0
        for i in range(1, n + 1):
            ans ^= i
        for num in nums:
            ans ^= num
        return ans


```

---

### 🧠 Explanation:

- Using Properties of XOR i.e. a^a = 0, a^0 = a, a^b = a^b
- Calculate XOR of each number present in range [0, n]
- Calculate XOR of each number present in nums to itself

---

### ⏱️ Time Complexity:

- Time : O(n)
- Space : O(1)
