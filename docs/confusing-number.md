---
id: confusing-number
title: Confusing Number
sidebar_label: Confusing Number
---
## Description
<div class="description">
null
</div>

## Solution(python3)
```python3
class Solution:
    def confusingNumber(self, n: int) -> bool:
        t=n
        s=0
        while t:
            d=t%10
            t=int(t/10)
            if d in [2,3,4,5,7]:
                return False
            elif d==6:
                d2=9
            elif d==9:
                d2=6
            else:
                d2=d
            s=s*10+d2
    
        return n!=s
```