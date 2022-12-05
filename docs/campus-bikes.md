---
id: campus-bikes
title: Campus Bikes
sidebar_label: Campus Bikes
---
## Description
<div class="description">
null
</div>

## Solution(python3)
```python3
class Solution:
    def assignBikes(self, workers: List[List[int]], bikes: List[List[int]]) -> List[int]:
        ans, used = [-1] * len(workers), set()
        for d, w, b in sorted([abs(workers[i][0] - bikes[j][0]) + abs(workers[i][1] - bikes[j][1]), i, j] for i in range(len(workers)) for j in range(len(bikes))):
            if ans[w] == -1 and b not in used:
                ans[w] = b
                used.add(b)
        return ans
```