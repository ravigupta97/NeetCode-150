
## 🧠 Problem: Majority Element (LeetCode #169)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/majority-element/](https://leetcode.com/problems/majority-element/)


### ❓ Problem Statement:
Given an array nums of size n, return the majority element.

The majority element is the element that appears more than ⌊n / 2⌋ times. You may assume that the majority element always exists in the array.

 

Example 1:

- Input: nums = [3,2,3]
- Output: 3

Example 2:

- Input: nums = [2,2,1,1,1,2,2]
- Output: 2
 
Constraints:

- n == nums.length
- 1 <= n <= 5 * 104
- -109 <= nums[i] <= 109
 

Follow-up: Could you solve the problem in linear time and in O(1) space?

---

### ✅ Solution (Using Dictionary) (Python):
```python
class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        freq = {}

        for num in nums:
            freq[num] = freq.get(num,0) + 1

        for key, val in freq.items():
            if val > (len(nums))//2:
                return key
        
        return 0
```

---

### 🧠 Explanation:

- Initialize a dict and store the elements of the list as key and its occurence count as value
- Iterate over the dictionary and check if the any key has value which is greater than n/2
- If yes return the corrosponding key as majority element

---

### ⏱️ Time Complexity:

- Time : O(n)
- Space : O(n)

---

### ✅ Solution (Using Boyer-Moore Voting Algorithm) (Python):
```python
class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        count = 0
        candidate = None

        for num in nums:
            if count == 0:
                candidate = num
            
            if num == candidate:
                count += 1
            else:
                count += -1
        
        return candidate
```

---

### 🧠 Explanation:

- We use this algo with the intution that, If an element is the majority, it will survive the cancellation of all other elements.
- When count is 0, choose the current number as a new candidate.
- If the next number is the same as the candidate, increase count.
- Otherwise, decrease count.
- In the end, the majority element remains because it appears more than n/2 times.

---

### ⏱️ Time Complexity:

- Time : O(n)
- Space : O(1)
