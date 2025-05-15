
## 🧠 Problem: Valid Parentheses (LeetCode #20)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/valid-parentheses/description](https://leetcode.com/problems/valid-parentheses/description/)


### ❓ Problem Statement:
Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

Open brackets must be closed by the same type of brackets.
Open brackets must be closed in the correct order.
Every close bracket has a corresponding open bracket of the same type.
 

Example 1:

Input: s = "()"

Output: true

Example 2:

Input: s = "()[]{}"

Output: true

Example 3:

Input: s = "(]"

Output: false

Example 4:

Input: s = "([])"

Output: true

 

Constraints:

- 1 <= s.length <= 104
- s consists of parentheses only '()[]{}'.


---

### ✅ Solution (Python):
```python
class Solution:
    def isValid(self, s: str) -> bool:
        #Dictionary to store matching brackets
        brackets = {')' : '(', '}':'{',']' : '['}
        # Stack to keep tarck of opening brackets 
        stack = []
        # Iterate through each character in a string
        for char in s:
            # If its a closing bracket
            if char in brackets:
                #check if stack is empty or top doesn't match
                if not stack or stack[-1] != brackets[char]:
                    return False
                #pop the matching opening bracket
                stack.pop()
            else:
                #push opening bracket into stack
                stack.append(char)
        # return True if stack is empty, false if not
        return len(stack) == 0

        
```

---

### 🧠 Explanation:

- Use Dictionary to store the brackets in the string
- Use stack to keep track of the opening brackets
- Iterate through the char of string and check if its a closing bracket or top doesn't match
- pop the opening matching bracket else push opening bracket
- If stack is empty return True, otherwise False

---

⏱️ Time Complexity:

- Time : O(n)
- Space : O(n)
