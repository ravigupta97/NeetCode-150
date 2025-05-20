
## 🧠 Problem: Reverse String (LeetCode #344)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/reverse-string/](https://leetcode.com/problems/reverse-string/)


### ❓ Problem Statement:
Write a function that reverses a string. The input string is given as an array of characters s.

You must do this by modifying the input array in-place with O(1) extra memory.

 

Example 1:

- Input: s = ["h","e","l","l","o"]
- Output: ["o","l","l","e","h"]

Example 2:

- Input: s = ["H","a","n","n","a","h"]
- Output: ["h","a","n","n","a","H"]
 

Constraints:

- 1 <= s.length <= 105
- s[i] is a printable ascii character.

---

### ✅ Solution (Python):
```python
class Solution:
    def reverseString(self, s: List[str]) -> None:
        left = 0
        right = len(s) - 1

        while left < right:
            s[left], s[right] = s[right], s[left]
            left += 1
            right -= 1
        
```

---

### 🧠 Explanation:

- Use Two Pointer Approach one from left and other from right
- Iterate through the list 
- Swap the left and right strings in the list
- move the left pointer forward and right pointer backwards


---

### ⏱️ Time Complexity:

- Time : O(n)
- Space : O(1)
