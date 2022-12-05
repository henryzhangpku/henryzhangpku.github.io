---
id: max-consecutive-ones-ii
title: Max Consecutive Ones II
sidebar_label: Max Consecutive Ones II
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def findMaxConsecutiveOnes(self, nums):
        result, prev, curr = 0, 0, 0
        for n in nums:
            if n == 0:
                result = max(result, prev+curr+1)
                prev, curr = curr, 0
            else:
                curr += 1
        return min(max(result, prev+curr+1), len(nums))

```