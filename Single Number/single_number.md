
## 🧠 Problem: Single Number (LeetCode #136)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/single-number/](https://leetcode.com/problems/single-number/)


### ❓ Problem Statement:
Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

 

Example 1:

- Input: nums = [2,2,1]
- Output: 1

Example 2:

- Input: nums = [4,1,2,1,2]
- Output: 4

Example 3:

- Input: nums = [1]
- Output: 1


Constraints:

- 1 <= nums.length <= 3 * 104
- -3 * 104 <= nums[i] <= 3 * 104
- Each element in the array appears twice except for one element which appears only once.
  
---

### ✅ Solution (Using Dictionary) (Python):
- This Solution is not the right one from the leetcode point of view as it uses extra space and in the question there is constraint to use extra space but can be used as an interview approach
```python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        # Initialize a empty dictionary to store the number as key and its occurence frequency as its value 
        freq = {}

        # Iterate over the list
        for num in nums:
            # Count the occurence frequency of each number of the list and store it in dict
            freq[num] = freq.get(num, 0) + 1

        # Iterate over the dict and return the key which has frequency 1
        for key in freq:
            if freq[key] == 1:
                return key
```

---

### 🧠 Explanation:

- Initialize a empty dictionary to store the number as key and its occurence frequency as its value 
- Iterate over the list and Count the occurence frequency of each number of the list and store it in dict
- Iterate over the dict and return the key which has frequency 1

---

### ⏱️ Time Complexity:

- Time : O(n)
- Space : O(n)

---

### ✅ Solution (Using XOR) (Python):
- This solution fulfills the constraint condition of not using extra space

```python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        ans = 0

        # Iterate over the list and XOR each number and return the result
        for num in nums:
            ans ^= num
        return ans
```

---

### 🧠 Explanation:

- This solution is using XOR which has property that a^a = 0(any number XOR itself is 0) and a^0 = a
- XOR is commutative and associative
- Iterate over the list and XOR each number and return the result

---

### ⏱️ Time Complexity:

- Time : O(n)
- Space : O(1)
