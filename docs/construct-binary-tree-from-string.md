---
id: construct-binary-tree-from-string
title: Construct Binary Tree from String
sidebar_label: Construct Binary Tree from String
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
    def str2tree(self, s):
        def helper(s, i):
            start = i
            if s[i] == '-': i += 1
            while i < len(s) and s[i].isdigit(): i += 1
            node = TreeNode(int(s[start:i]))
            if i < len(s) and s[i] == '(':
                i += 1
                node.left, i = helper(s, i)
                i += 1
            if i < len(s) and s[i] == '(':
                i += 1
                node.right, i = helper(s, i)
                i += 1
            return node, i

        return helper(s, 0)[0] if s else None

        
```