---
id: index-pairs-of-a-string
title: Index Pairs of a String
sidebar_label: Index Pairs of a String
---
## Description
<div class="description">
null
</div>

## Solution(python3)
```python3
class Solution:
    def indexPairs(self, text: str, words: List[str]) -> List[List[int]]:
        r=[]
        for i in range(0, len(text)):
            for w in words:
                if text[i:i+len(w)]==w:
                    r.append([i,i+len(w)-1])
        r.sort()          
        return r
```