---
id: 3sum-smaller
title: 3Sum Smaller
sidebar_label: 3Sum Smaller
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def threeSumSmaller(self, nums, target):
        nums.sort()
        n = len(nums)

        count, k = 0, 2
        while k < n:
            i, j = 0, k - 1
            while i < j:  # Two Pointers, linear time.
                if nums[i] + nums[j] + nums[k] >= target:
                    j -= 1
                else:
                    count += j - i
                    i += 1
            k += 1

        return count
        
```