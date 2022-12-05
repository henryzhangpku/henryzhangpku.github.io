---
id: find-leaves-of-binary-tree
title: Find Leaves of Binary Tree
sidebar_label: Find Leaves of Binary Tree
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def findLeaves(self, root):
        def helper(node, result):
            if not node:
                return -1
            level = 1 + max(helper(node.left, result), \
                            helper(node.right, result))
            if len(result) < level + 1:
                result.append([])
            result[level].append(node.val)
            return level

        result = []
        helper(root, result)
        return result
        
```