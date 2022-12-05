---
id: nested-list-weight-sum
title: Nested List Weight Sum
sidebar_label: Nested List Weight Sum
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
# """
# This is the interface that allows for creating nested lists.
# You should not implement it, or speculate about its implementation
# """
#class NestedInteger(object):
#    def isInteger(self):
#        """
#        @return True if this NestedInteger holds a single integer, rather than a nested list.
#        :rtype bool
#        """
#
#    def getInteger(self):
#        """
#        @return the single integer that this NestedInteger holds, if it holds a single integer
#        Return None if this NestedInteger holds a nested list
#        :rtype int
#        """
#
#    def getList(self):
#        """
#        @return the nested list that this NestedInteger holds, if it holds a nested list
#        Return None if this NestedInteger holds a single integer
#        :rtype List[NestedInteger]
#        """

class Solution(object):
    def depthSum(self, nestedList):
        def helper(nestedList, d):
            res=0
            for l in nestedList:
                if l.isInteger():
                    res+= l.getInteger()*d
                else:
                    res+= helper(l.getList(),d+1)
            return res
        return helper(nestedList,1)

        
        
```