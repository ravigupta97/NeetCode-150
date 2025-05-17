
## 🧠 Problem: Valid Palindrome (LeetCode #125)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/valid-palindrome/description/](https://leetcode.com/problems/valid-palindrome/description/)


### ❓ Problem Statement:
A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.

 

Example 1:

- Input: s = "A man, a plan, a canal: Panama"
- Output: true
- Explanation: "amanaplanacanalpanama" is a palindrome.

Example 2:

- Input: s = "race a car"
- Output: false
- Explanation: "raceacar" is not a palindrome.

Example 3:

- Input: s = " "
- Output: true
- Explanation: s is an empty string "" after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.
 

Constraints:

- 1 <= s.length <= 2 * 105
- s consists only of printable ASCII characters.

---

### ✅ Solution (Python):
```python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        # Convert the string and remove all the non-alphanumeric characters 
        s = ''.join(c for c in s if c.isalnum())
        # Convert the string into all lower case
        required_string = s.lower()
        # Reverse the converted string 
        reverse_str = required_string[::-1]
        
        # Check if the reversed string is same as converted string or not
        if required_string == reverse_str:
            return True
        else:
            return False
        
```

---

### 🧠 Explanation:

- Convert the string and remove all the non-alphanumeric characters
- Convert the string into all lower case
- Reverse the converted string 
- Check if the reversed string is same as converted string or not

---

⏱️ Time Complexity:

- Time : O(n)
