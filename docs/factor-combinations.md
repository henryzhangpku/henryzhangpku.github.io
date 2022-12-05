---
id: factor-combinations
title: Factor Combinations
sidebar_label: Factor Combinations
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def getFactors(self, n):
        result = []
        factors = []
        self.helper(n, result, factors)
        return result

    def helper(self, n, result, factors):
        i = 2 if not factors else factors[-1]
        while i <= n / i:
            if n % i == 0:
                factors.append(i);
                factors.append(n / i);
                result.append(list(factors));
                factors.pop();
                self.helper(n / i, result, factors);
                factors.pop()
            i += 1
        
```