---
id: sentence-similarity
title: Sentence Similarity
sidebar_label: Sentence Similarity
---
## Description
<div class="description">
null
</div>

## Solution(python3)
```python3
class Solution:
    def areSentencesSimilar(self, sentence1: List[str], sentence2: List[str], similarPairs: List[List[str]]) -> bool:
        if len(sentence1)!=len(sentence2):
            return False
        for i in range(len(sentence1)):
            if sentence1[i]==sentence2[i]:
                continue 
            elif [sentence1[i], sentence2[i]] not in similarPairs and [sentence2[i], sentence1[i]] not in similarPairs:
                return False
        return True
                
            
```