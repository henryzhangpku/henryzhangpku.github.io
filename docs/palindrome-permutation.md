---
id: palindrome-permutation
title: Palindrome Permutation
sidebar_label: Palindrome Permutation
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def canPermutePalindrome(self, s):
        return sum(v % 2 for v in collections.Counter(s).values()) <  2
        
```