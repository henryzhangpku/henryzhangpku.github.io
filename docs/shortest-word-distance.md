---
id: shortest-word-distance
title: Shortest Word Distance
sidebar_label: Shortest Word Distance
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def shortestDistance(self, words, word1, word2):
        dist = float("inf")
        i, index1, index2 = 0, None, None
        while i < len(words):
            if words[i] == word1:
                index1 = i
            elif words[i] == word2:
                index2 = i

            if index1 is not None and index2 is not None:
                dist = min(dist, abs(index1 - index2))
            i += 1

        return dist
        
```