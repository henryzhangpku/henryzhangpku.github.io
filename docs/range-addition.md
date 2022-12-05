---
id: range-addition
title: Range Addition
sidebar_label: Range Addition
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def getModifiedArray(self, length, updates):
        """
        :type length: int
        :type updates: List[List[int]]
        :rtype: List[int]
        """
        result=[0]*length
        for update in updates:
            result[update[0]]+=update[2]
            if update[1]+1 < length:
                result[update[1]+1]-=update[2]
        for i in range(1,length):
            result[i]+=result[i-1]
        return result
```