
## 🧠 Problem: Middle of the Linked List (LeetCode #876)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/middle-of-the-linked-list/](https://leetcode.com/problems/middle-of-the-linked-list/)


### ❓ Problem Statement:
Given the head of a singly linked list, return the middle node of the linked list.

If there are two middle nodes, return the second middle node.

 
Example 1:

![image](https://github.com/user-attachments/assets/d27b0505-fc91-45bc-b3d5-d806be38c946)

- Input: head = [1,2,3,4,5]
- Output: [3,4,5]
- Explanation: The middle node of the list is node 3.

Example 2:

![image](https://github.com/user-attachments/assets/e4ad1e1a-9635-48c7-a686-422258159df4)

- Input: head = [1,2,3,4,5,6]
- Output: [4,5,6]
- Explanation: Since the list has two middle nodes with values 3 and 4, we return the second one.
 

Constraints:

- The number of nodes in the list is in the range [1, 100].
- 1 <= Node.val <= 100

---

### ✅ Solution (Python):
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
        slow = head
        fast = head

        while fast and fast.next:
            slow = slow.next

            fast = fast.next.next

        return slow
```

---

### 🧠 Explanation:

- Use Two Pointer Approach
- Intitialize two pointers slow and fast with starting node as head
- move slow pointer with one step
- move fast pointer with two steps
- when the fast will reach the end of the list the slow pointer will be at the middle return it

---

### ⏱️ Time Complexity:

- Time : O(n)
- Space : O(1)
