---
id: longest-substring-with-at-most-k-distinct-characters
title: Longest Substring with At Most K Distinct Characters
sidebar_label: Longest Substring with At Most K Distinct Characters
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def lengthOfLongestSubstringKDistinct(self, s, k):
        longest, start, distinct_count, visited = 0, 0, 0, [0 for _ in xrange(256)]
        for i, char in enumerate(s):
            if visited[ord(char)] == 0:
                distinct_count += 1
            visited[ord(char)] += 1
            
            while distinct_count > k:
                visited[ord(s[start])] -= 1
                if visited[ord(s[start])] == 0:
                    distinct_count -= 1
                start += 1
  
            longest = max(longest, i - start + 1)
        return longest

        
```