---
id: flatten-2d-vector
title: Flatten 2D Vector
sidebar_label: Flatten 2D Vector
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Vector2D(object):

    def __init__(self, vec2d):
        self.vec=vec2d
        self.x=0
        if self.x!=len(self.vec):
            self.y=0
            self.adjustNextIter()

    def next(self):
        ret=self.vec[self.x][self.y]
        self.y+=1
        self.adjustNextIter()
        return ret
        

    def hasNext(self):
        return self.x!=len(self.vec) and self.y!=len(self.vec[self.x])
    
    def adjustNextIter(self):
        while self.x != len(self.vec) and self.y == len(self.vec[self.x]):
            self.x+=1
            if self.x != len(self.vec):
                self.y=0

# Your Vector2D object will be instantiated and called as such:
# i, v = Vector2D(vec2d), []
# while i.hasNext(): v.append(i.next())
```