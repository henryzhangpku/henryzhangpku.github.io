---
id: meeting-rooms
title: Meeting Rooms
sidebar_label: Meeting Rooms
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
# Definition for an interval.
# class Interval(object):
#     def __init__(self, s=0, e=0):
#         self.start = s
#         self.end = e

class Solution(object):
    def canAttendMeetings(self, intervals):
        intervals.sort(key=lambda x: x.start) #sort by start first
        
        for i in xrange(1,len(intervals)):
            if intervals[i].start < intervals[i-1].end: #conflict checking
                return False
        return True
```