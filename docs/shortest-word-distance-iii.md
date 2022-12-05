---
id: shortest-word-distance-iii
title: Shortest Word Distance III
sidebar_label: Shortest Word Distance III
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def shortestWordDistance(self, words, word1, word2):
        dist=float('inf')
        is_same = (word1==word2)
        i,i1,i2=0,None,None
        while i<len(words):
            if words[i]==word1:
                if is_same and i1 is not None:
                    dist=min(dist,abs(i1-i))
                i1=i
            elif words[i]==word2:
                i2=i
            if i1 is not None and i2 is not None:
                dist =min(dist, abs(i1-i2))
            i+=1
        return dist
        
```