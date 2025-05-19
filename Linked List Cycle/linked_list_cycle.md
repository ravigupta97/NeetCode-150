
## 🧠 Problem: Linked List Cycle (LeetCode #141)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/linked-list-cycle/description/](https://leetcode.com/problems/linked-list-cycle/description/)


### ❓ Problem Statement:
Given head, the head of a linked list, determine if the linked list has a cycle in it.

There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the next pointer. Internally, pos is used to denote the index of the node that tail's next pointer is connected to. Note that pos is not passed as a parameter.

Return true if there is a cycle in the linked list. Otherwise, return false.



Example 1:

![image](https://github.com/user-attachments/assets/00c1fc2d-5c3e-4b91-a1c9-ce76156dd8c9)

- Input: head = [3,2,0,-4], pos = 1
- Output: true
- Explanation: There is a cycle in the linked list, where the tail connects to the 1st node (0-indexed).

Example 2:

![image](https://github.com/user-attachments/assets/5dce9056-fcdd-4088-aeb3-88286b8718ca)

- Input: head = [1,2], pos = 0
- Output: true
- Explanation: There is a cycle in the linked list, where the tail connects to the 0th node.

Example 3:

![image](https://github.com/user-attachments/assets/c41ea70f-2c66-4842-aade-52aaa0b4f2cb)

- Input: head = [1], pos = -1
- Output: false
- Explanation: There is no cycle in the linked list.
 

Constraints:

- The number of the nodes in the list is in the range [0, 104].
- -105 <= Node.val <= 105
- pos is -1 or a valid index in the linked-list.

---

### ✅ Solution (Python):
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def hasCycle(self, head: Optional[ListNode]) -> bool:
        # Intitialize two pointers slow and fast with starting node as head
        slow = head
        fast = head

        while fast is not None and fast.next is not None:
            # move slow pointer with one step
            slow = slow.next
            # move fast pointer with two steps
            fast = fast.next.next

            # If there is a loop in the linked list then both pointers will meet eventully
            if slow == fast:
                return True
        
        return False
```

---

### 🧠 Explanation:

- Use Two Pointer Approach
- Intitialize two pointers slow and fast with starting node as head
- move slow pointer with one step
- move fast pointer with two steps
- If there is a loop in the linked list then both pointers will meet eventully

---

### ⏱️ Time Complexity:

- Time : O(n)
- Space : O(1)
