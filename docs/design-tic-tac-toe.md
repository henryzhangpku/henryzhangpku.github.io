---
id: design-tic-tac-toe
title: Design Tic-Tac-Toe
sidebar_label: Design Tic-Tac-Toe
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class TicTacToe(object):
    def __init__(self, n):
        self.__rows = [[0, 0] for _ in xrange(n)]
        self.__cols = [[0, 0] for _ in xrange(n)]
        self.__diagonal = [0, 0]
        self.__anti_diagonal = [0, 0]
    def move(self, row, col, player):
        i = player - 1
        self.__rows[row][i] += 1
        self.__cols[col][i] += 1
        if row == col:
            self.__diagonal[i] += 1
        if col == len(self.__rows) - row - 1:
            self.__anti_diagonal[i] += 1
        if any([self.__rows[row][i] == len(self.__rows), \
                self.__cols[col][i] == len(self.__cols), \
                self.__diagonal[i] == len(self.__rows), \
                self.__anti_diagonal[i] == len(self.__cols)]):
            return player

        return 0
```