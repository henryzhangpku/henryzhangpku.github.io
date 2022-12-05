---
id: robot-room-cleaner
title: Robot Room Cleaner
sidebar_label: Robot Room Cleaner
---
## Description
<div class="description">
null
</div>

## Solution(python3)
```python3
# """
# This is the robot's control interface.
# You should not implement it, or speculate about its implementation
# """
#class Robot:
#    def move(self):
#        """
#        Returns true if the cell in front is open and robot moves into the cell.
#        Returns false if the cell in front is blocked and robot stays in the current cell.
#        :rtype bool
#        """
#
#    def turnLeft(self):
#        """
#        Robot will stay in the same cell after calling turnLeft/turnRight.
#        Each turn will be 90 degrees.
#        :rtype void
#        """
#
#    def turnRight(self):
#        """
#        Robot will stay in the same cell after calling turnLeft/turnRight.
#        Each turn will be 90 degrees.
#        :rtype void
#        """
#
#    def clean(self):
#        """
#        Clean the current cell.
#        :rtype void
#        """

class Solution:
    def cleanRoom(self, robot):
        """
        :type robot: Robot
        :rtype: None
        """
        
        def go_back(): 
            robot.turnLeft()
            robot.turnLeft()
            robot.move()            
            robot.turnRight()
            robot.turnRight()

        def backtracking(cell, direction, visited):
            if cell in visited:
                return
            
            visited.add(cell)
            
            robot.clean()
            
            for i in range(0, 4):
                new_diretion = (direction + i) % 4
                new_cell = (cell[0] + directions[new_diretion][0],
                            cell[1] + directions[new_diretion][1])
                
                if robot.move():
                    backtracking(new_cell, new_diretion, visited)
                    go_back()
                    
                robot.turnRight()

        directions = [(0, 1), (1, 0), (0, -1), (-1, 0)]        
        backtracking((0, 0), 0, set())
```