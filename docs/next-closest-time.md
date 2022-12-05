---
id: next-closest-time
title: Next Closest Time
sidebar_label: Next Closest Time
---
## Description
<div class="description">
null
</div>

## Solution(python3)
```python3
class Solution:
    def nextClosestTime(self, time: str) -> str:
        time = time[0:2]+time[3:]
        
        def find_larger(temp, comp):
            for i in sorted(time):
                if i < temp[0]: continue
                for j in sorted(time):
                    if i+j > temp and i+j < comp:
                        return i+j
            return "99"
        
        new_min = find_larger(time[2:], "60")
        if new_min != "99":
            return time[0:2] + ":" + new_min
        
        new_hour = find_larger(time[:2], "24")
        dig = min(time)
        if new_hour != "99":
            return new_hour + ":" + dig + dig
        return dig + dig + ":" + dig + dig
```