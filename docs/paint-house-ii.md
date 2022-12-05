---
id: paint-house-ii
title: Paint House II
sidebar_label: Paint House II
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def minCostII(self, costs):
        if not costs:
            return 0
        
        n = len(costs)
        k = len(costs[0])
        min_cost = [costs[0], [0] * k]
        for i in xrange(1, n):
            smallest, second_smallest = float("inf"), float("inf")
            for j in xrange(k):
                if min_cost[(i - 1) % 2][j] < smallest:
                    smallest, second_smallest = min_cost[(i - 1) % 2][j], smallest
                elif min_cost[(i - 1) % 2][j] < second_smallest:
                    second_smallest = min_cost[(i - 1) % 2][j]
            for j in xrange(k):
                min_j = smallest if min_cost[(i - 1) % 2][j] != smallest else second_smallest
                min_cost[i % 2][j] = costs[i][j] + min_j

        return min(min_cost[(n - 1) % 2])
        
```