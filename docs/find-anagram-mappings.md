---
id: find-anagram-mappings
title: Find Anagram Mappings
sidebar_label: Find Anagram Mappings
---
## Description
<div class="description">
null
</div>

## Solution(python3)
```python3
class Solution:
    def anagramMappings(self, nums1: List[int], nums2: List[int]) -> List[int]:
        m={}
        r={}
        for i in range(0, len(nums2)):
            x=nums2[i]
            if x in m:
                m[x].append(i)
            else:
                m[x]=[i]
        for j in range(0, len(nums1)):
            x=nums1[j]
            if len(m[x])==1:
                r[m[x][0]]=j
            else:
                r[m[x][0]]=j
                m[x].pop(0)
        return r
                
            
           
```