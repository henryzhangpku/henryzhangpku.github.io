---
id: single-row-keyboard
title: Single-Row Keyboard
sidebar_label: Single-Row Keyboard
---
## Description
<div class="description">
null
</div>

## Solution(python3)
```python3
class Solution:
    def calculateTime(self, keyboard: str, word: str) -> int:
        dic={}
        for i in range(len(keyboard)):
            dic[keyboard[i]]=i
        res=dic[word[0]]
        for j in range(1,len(word)):
            c=word[j]
            res+= abs(dic[word[j-1]]-dic[word[j]])
        return res
```