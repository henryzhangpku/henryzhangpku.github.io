---
id: largest-unique-number
title: Largest Unique Number
sidebar_label: Largest Unique Number
---
## Description
<div class="description">
null
</div>

## Solution(python3)
```python3
class Solution:
    def largestUniqueNumber(self, nums: List[int]) -> int:
        ht={}
        for x in nums:
            if x in ht:
                ht[x]+=1
            else:
                ht[x]=1
        
        for k in reversed(sorted(ht)):
            if ht[k]==1:
                return k
        return -1
```