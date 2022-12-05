---
id: line-reflection
title: Line Reflection
sidebar_label: Line Reflection
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def isReflected(self, points):
        if not points:
            return True
        d_y = collections.defaultdict(set) #dict of set
        l, r = float("inf"), float("-inf")
        for p in points:
            d_y[p[1]].add(p[0])
            l, r = min(l, p[0]), max(r, p[0]) #min/max of X
        m = l + r
        for xs in d_y.values():
            for x in xs:
                if m - x not in xs:
                    return False
        return True
        
```