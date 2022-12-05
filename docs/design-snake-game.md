---
id: design-snake-game
title: Design Snake Game
sidebar_label: Design Snake Game
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
# Time:  O(1) per move
# Space: O(s), s is the current length of the snake.
from collections import deque
class SnakeGame(object):
    def __init__(self, width,height,food):
        self.__width = width
        self.__height = height
        self.__score = 0
        self.__food = deque(food)
        self.__snake = deque([(0, 0)])
        self.__direction =  {"U":(-1, 0), "L":(0, -1), "R":(0, 1), "D":(1, 0)};
        self.__lookup = collections.defaultdict(int)
        self.__lookup[(0, 0)] += 1     
    def move(self, direction):
        def valid(x, y):
            return 0 <= x < self.__height and \
                   0 <= y < self.__width and \
                   (x, y) not in self.__lookup
        d = self.__direction[direction]
        x, y = self.__snake[-1][0] + d[0], self.__snake[-1][1] + d[1]

        tail = self.__snake[-1]
        self.__lookup[self.__snake[0]] -= 1
        if self.__lookup[self.__snake[0]] == 0:
            self.__lookup.pop(self.__snake[0])
        self.__snake.popleft()
        if not valid(x, y):
            return -1
        elif self.__food and (self.__food[0][0], self.__food[0][1]) == (x, y):
            self.__score += 1
            self.__food.popleft()
            self.__snake.appendleft(tail)
            self.__lookup[tail] += 1
        self.__snake += (x, y),
        self.__lookup[(x, y)] += 1
        return self.__score
```