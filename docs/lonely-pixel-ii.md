---
id: lonely-pixel-ii
title: Lonely Pixel II
sidebar_label: Lonely Pixel II
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def findBlackPixel(self, picture, N):
        rows, cols = [0] * len(picture),  [0] * len(picture[0])
        lookup = collections.defaultdict(int)
        for i in xrange(len(picture)):
            for j in xrange(len(picture[0])):
                if picture[i][j] == 'B':
                    rows[i] += 1
                    cols[j] += 1
            lookup[tuple(picture[i])] += 1

        result = 0
        for i in xrange(len(picture)):
            if rows[i] == N and lookup[tuple(picture[i])] == N:
                for j in xrange(len(picture[0])):
                     result += picture[i][j] == 'B' and cols[j] == N
        return result
        
```