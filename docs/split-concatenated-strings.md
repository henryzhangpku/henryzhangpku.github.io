---
id: split-concatenated-strings
title: Split Concatenated Strings
sidebar_label: Split Concatenated Strings
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def splitLoopedString(self, strs):
        tmp = []
        for s in strs:
            tmp += max(s, s[::-1])
        s = "".join(tmp)

        result, st = "a", 0
        for i in xrange(len(strs)):
            body = "".join([s[st + len(strs[i]):], s[0:st]])
            for p in strs[i], strs[i][::-1]:
                for j in xrange(len(strs[i])):
                    if p[j] >= result[0]:
                        result = max(result, "".join([p[j:], body, p[:j]]))
            st += len(strs[i])
        return result

        
```