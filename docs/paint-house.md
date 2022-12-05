---
id: paint-house
title: Paint House
sidebar_label: Paint House
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def minCost(self, costs):
        if not costs:
            return 0
        
        min_cost = [costs[0], [0, 0, 0]]
        
        n = len(costs)
        for i in xrange(1, n):
            min_cost[i % 2][0] = costs[i][0] + \
                                 min(min_cost[(i - 1) % 2][1], min_cost[(i - 1) % 2][2])
            min_cost[i % 2][1] = costs[i][1] + \
                                 min(min_cost[(i - 1) % 2][0], min_cost[(i - 1) % 2][2])
            min_cost[i % 2][2] = costs[i][2] + \
                                 min(min_cost[(i - 1) % 2][0], min_cost[(i - 1) % 2][1])

        return min(min_cost[(n - 1) % 2])
```