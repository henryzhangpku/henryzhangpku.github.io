---
id: plus-one-linked-list
title: Plus One Linked List
sidebar_label: Plus One Linked List
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution(object):
    def plusOne(self, head):
        if not head:
            return None

        dummy = ListNode(0)
        dummy.next = head

        left, right = dummy, head
        while right.next:
            if right.val != 9:
                left = right
            right = right.next

        if right.val != 9:
            right.val += 1
        else:
            left.val += 1
            right = left.next
            while right:
                right.val = 0
                right = right.next

        return dummy if dummy.val else dummy.next
        
```