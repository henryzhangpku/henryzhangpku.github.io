---
id: lonely-pixel-i
title: Lonely Pixel I
sidebar_label: Lonely Pixel I
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def findLonelyPixel(self, picture):
        rows, cols = [0] * len(picture),  [0] * len(picture[0])
        for i in xrange(len(picture)):
            for j in xrange(len(picture[0])):
                if picture[i][j] == 'B':
                    rows[i] += 1
                    cols[j] += 1

        result = 0
        for i in xrange(len(picture)):
            if rows[i] == 1:
                for j in xrange(len(picture[0])):
                     result += picture[i][j] == 'B' and cols[j] == 1
        return result
        
```