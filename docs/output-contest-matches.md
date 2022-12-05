---
id: output-contest-matches
title: Output Contest Matches
sidebar_label: Output Contest Matches
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def findContestMatch(self, n):
        matches = map(str, range(1, n+1))
        while len(matches)/2:
            matches = ["({},{})".format(matches[i], matches[-i-1]) for i in xrange(len(matches)/2)]
        return matches[0]
 
```