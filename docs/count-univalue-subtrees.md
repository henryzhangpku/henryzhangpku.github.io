---
id: count-univalue-subtrees
title: Count Univalue Subtrees
sidebar_label: Count Univalue Subtrees
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution(object):
    def countUnivalSubtrees(self, root):
        [is_uni, count] = self.isUnivalSubtrees(root, 0);
        return count;

    def isUnivalSubtrees(self, root, count):
        if not root:
            return [True, count]

        [left, count] = self.isUnivalSubtrees(root.left, count)
        [right, count] = self.isUnivalSubtrees(root.right, count)
        if self.isSame(root, root.left, left) and \
           self.isSame(root, root.right, right):
                count += 1
                return [True, count]

        return [False, count]
    
    def isSame(self, root, child, is_uni):
        return not child or (is_uni and root.val == child.val)

        
```