---
id: find-permutation
title: Find Permutation
sidebar_label: Find Permutation
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def findPermutation(self, s):
        result = []
        for i in xrange(len(s)+1):
            if i == len(s) or s[i] == 'I':
                result += range(i+1, len(result), -1)
        return result

        
```