---
id: logger-rate-limiter
title: Logger Rate Limiter
sidebar_label: Logger Rate Limiter
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
# Time:  O(1), amortized
# Space: O(k), k is the max number of printed messages in last 10 seconds
class Logger(object):
    def __init__(self):
        self.ht={}   

    def shouldPrintMessage(self, timestamp, message):
        if timestamp < self.ht.get(message,0):
            return False 
        self.ht[message]= timestamp + 10  #update to next min timestamp
        return True
     
```