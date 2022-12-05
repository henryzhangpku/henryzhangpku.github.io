---
id: strobogrammatic-number-ii
title: Strobogrammatic Number II
sidebar_label: Strobogrammatic Number II
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    lookup = {'0':'0', '1':'1', '6':'9', '8':'8', '9':'6'}
    def findStrobogrammatic(self, n):
        return self.helper(n, n)

    def helper(self, n, k):
        if k == 0:
            return ['']
        elif k == 1:
            return ['0', '1', '8']
        
        result = []
        for num in self.helper(n, k - 2):
            for key, val in self.lookup.iteritems():
                if n != k or key != '0':
                    result.append(key + num + val)

        return result
        
```