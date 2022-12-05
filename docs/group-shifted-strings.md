---
id: group-shifted-strings
title: Group Shifted Strings
sidebar_label: Group Shifted Strings
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def groupStrings(self, strings):
        groups = collections.defaultdict(list)
        for s in strings:
            groups[tuple((ord(c) - ord(s[0])) % 26 for c in s)] += s,
        return groups.values()
```