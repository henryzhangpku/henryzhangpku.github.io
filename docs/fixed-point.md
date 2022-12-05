---
id: fixed-point
title: Fixed Point
sidebar_label: Fixed Point
---
## Description
<div class="description">
null
</div>

## Solution(python3)
```python3
class Solution:
    def fixedPoint(self, arr: List[int]) -> int:
        for i in range(0, len(arr)):
            if arr[i]==i:
                return i
            
        return -1
                
```