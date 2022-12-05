---
id: verify-preorder-sequence-in-binary-search-tree
title: Verify Preorder Sequence in Binary Search Tree
sidebar_label: Verify Preorder Sequence in Binary Search Tree
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def verifyPreorder(self, preorder):
        low, i = float("-inf"), -1
        for p in preorder:
            if p < low:
                return False
            while i >= 0 and p > preorder[i]:
                low = preorder[i]
                i -= 1
            i += 1
            preorder[i] = p
        return True
        
```