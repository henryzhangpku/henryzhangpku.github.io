---
id: sort-transformed-array
title: Sort Transformed Array
sidebar_label: Sort Transformed Array
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def sortTransformedArray(self, nums, a, b, c):
        f = lambda x, a, b, c : a * x * x + b * x + c

        result = []
        if not nums:
            return result

        left, right = 0, len(nums) - 1
        d = -1 if a > 0 else 1
        while left <= right:
            if d * f(nums[left], a, b, c) < d * f(nums[right], a, b, c):
                result.append(f(nums[left], a, b, c))
                left += 1
            else:
                result.append(f(nums[right], a, b, c))
                right -= 1

        return result[::d]
        
```