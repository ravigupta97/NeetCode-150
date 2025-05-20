
## 🧠 Problem: Reverse Linked List (LeetCode #206)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/reverse-linked-list/](https://leetcode.com/problems/reverse-linked-list/)


### ❓ Problem Statement:
Given the head of a singly linked list, reverse the list, and return the reversed list.

 
Example 1:

![image](https://github.com/user-attachments/assets/0529c266-ece8-4af5-bdfa-48e7a839bda2)

- Input: head = [1,2,3,4,5]
- Output: [5,4,3,2,1]

Example 2:

![image](https://github.com/user-attachments/assets/eeec096d-c404-45ff-8853-cdbb7634e40e)

- Input: head = [1,2]
- Output: [2,1]

Example 3:

- Input: head = []
- Output: []
 

Constraints:

- The number of nodes in the list is the range [0, 5000].
- -5000 <= Node.val <= 5000
 

Follow up: A linked list can be reversed either iteratively or recursively. Could you implement both?

---

### ✅ Solution (Python):
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        # Initialize prev as None
        prev = None
        # Initialize curr at the head of the list
        curr = head

        while curr:
            # Store the next node
            temp = curr.next
            # Reverse the pointer
            curr.next = prev
            # Move prev forward
            prev = curr
            # Move curr forward
            curr = temp
        
        # Now prev is the new head of reversed list
        return prev
```

---

### 🧠 Explanation:

- Use two pointers: prev (starts as null) and curr (starts at head).
- At each step:
   - Store curr.next in temp.
   - Reverse curr.next to point to prev.
   - Move prev to curr and curr to temp.
- Repeat until curr is null.
- prev becomes the new head of the reversed list.

---

### ⏱️ Time Complexity:

- Time : O(n)
- Space : O(1)
