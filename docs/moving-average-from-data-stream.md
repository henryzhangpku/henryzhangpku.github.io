---
id: moving-average-from-data-stream
title: Moving Average from Data Stream
sidebar_label: Moving Average from Data Stream
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class MovingAverage(object):
    def __init__(self, size):
        self.dq=collections.deque(maxlen=size)
    def next(self, val):
        self.dq.append(val)
        return float(sum(self.dq))/len(self.dq)
        
```