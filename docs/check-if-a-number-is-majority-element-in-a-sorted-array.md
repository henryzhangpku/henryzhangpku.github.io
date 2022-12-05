---
id: check-if-a-number-is-majority-element-in-a-sorted-array
title: Check If a Number Is Majority Element in a Sorted Array
sidebar_label: Check If a Number Is Majority Element in a Sorted Array
---
## Description
<div class="description">
null
</div>

## Solution(python3)
```python3
class Solution:
    def isMajorityElement(self, nums: List[int], target: int) -> bool:
        c=0
        n=len(nums)
        for i in range(n):
            if nums[i]==target:
                c+=1
        return c>n/2
                
                
        
```