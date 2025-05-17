

## 🧠 Problem: Valid Anagram (LeetCode #242)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/valid-anagram/description/](https://leetcode.com/problems/valid-anagram/description/)


### ❓ Problem Statement:
Given two strings s and t, return true if t is an anagram of s, and false otherwise.

 
Example 1:

- Input: s = "anagram", t = "nagaram"

- Output: true

Example 2:

- Input: s = "rat", t = "car"

- Output: false


Constraints:

- 1 <= s.length, t.length <= 5 * 104
- s and t consist of lowercase English letters.

---

### ✅ Solution (Sorting) (Python):
```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        # Sort both the strings and return true if both are same
        sorted_s = sorted(s)
        sorted_t = sorted(t)
        return sorted_s == sorted_t
```

---

### 🧠 Explanation:

- Sort Both the strings and then compare them
- If both are same then it will return True else False

---

⏱️ Time Complexity:

- Time : O(n log n)

---
### ✅ Solution (Using Dictionaries) (Python):
```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        # Initialize dict for each string
        freq_s = {}
        freq_t = {}

        # Count char frequencies and store it in dict with char as key and frequency as value
        for c in s:
            freq_s[c] = freq_s.get(c,0)+1

        for c in t:
            freq_t[c] = freq_t.get(c,0)+1

        # If both the dict are same then retuen true else false
        if freq_s == freq_t:
            return True
        else:
            return False 
        
```

---

### 🧠 Explanation:

- Initialize dict for each string
- Count char frequencies and store it in dict with char as key and frequency as value
- If both the dict are same then retuen true else false

---

⏱️ Time Complexity:

- Time : O(n)

