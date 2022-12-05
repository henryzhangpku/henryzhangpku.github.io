---
id: two-sum-less-than-k
title: Two Sum Less Than K
sidebar_label: Two Sum Less Than K
---
## Description
<div class="description">
null
</div>

## Solution(python3)
```python3
class Solution:
    def twoSumLessThanK(self, nums: List[int], k: int) -> int:
        nums.sort() #important to decide move directions 
        i=0
        j=len(nums)-1
        r=-1
        while i<j:
            s =nums[i]+nums[j]
            if s<k:
                r=max(r,s)
                i+=1
            else:
                j-=1
        return r
```