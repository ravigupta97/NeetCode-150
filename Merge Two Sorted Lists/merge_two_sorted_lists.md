

## 🧠 Problem: Merge Two Sorted Lists (LeetCode #21)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/merge-two-sorted-lists/description/](https://leetcode.com/problems/merge-two-sorted-lists/description/)


### ❓ Problem Statement:
You are given the heads of two sorted linked lists list1 and list2.

Merge the two lists into one sorted list. The list should be made by splicing together the nodes of the first two lists.

Return the head of the merged linked list.

 

Example 1:

![image](https://github.com/user-attachments/assets/5f56ef00-7ab0-4cb1-a456-aac224904940)

- Input: list1 = [1,2,4], list2 = [1,3,4]
- Output: [1,1,2,3,4,4]

Example 2:
- Input: list1 = [], list2 = []
- Output: []

Example 3:
- Input: list1 = [], list2 = [0]
- Output: [0]
 

Constraints:

- The number of nodes in both lists is in the range [0, 50].
- -100 <= Node.val <= 100
- Both list1 and list2 are sorted in non-decreasing order.

---

### ✅ Solution (Python):
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:
        #create a dummy node
        dummy = ListNode(0)
        curr = dummy

        #compare the nodes and add the smaller one to result
        while list1 and list2:
            if list1.val <= list2.val:
                curr.next = list1
                list1 = list1.next
            else:
                curr.next = list2
                list2 = list2.next
            curr = curr.next
        
        # Add remaining nodes of non empty list
        if list1:
            curr.next = list1
        if list2:
            curr.next = list2
        
        # return the merged list
        return dummy.next
       
```

---

### 🧠 Explanation:

- Compare both the lists and add smaller one to result list untill all nodes are done
- Use Two pointers, one for each list and one pointer for new merged list move these pointer as we build the merged list
- If one list ends before the other, we'll just add the rest of the other list to our result.

---

⏱️ Time Complexity:

- Time : O(n+m)

