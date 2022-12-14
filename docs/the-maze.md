---
id: the-maze
title: The Maze
sidebar_label: The Maze
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def hasPath(self, maze, start, destination):
        start, destination = tuple(start), tuple(destination)
        
        def neighbors(maze, node):
            for dir in [(-1, 0), (0, 1), (0, -1), (1, 0)]:
                cur_node, dist = list(node), 0
                while 0 <= cur_node[0]+dir[0] < len(maze) and \
                      0 <= cur_node[1]+dir[1] < len(maze[0]) and \
                      not maze[cur_node[0]+dir[0]][cur_node[1]+dir[1]]:
                    cur_node[0] += dir[0]
                    cur_node[1] += dir[1]
                    dist += 1
                yield dist, tuple(cur_node)

        queue = collections.deque([(0, start)])
        visited = set()
        while queue:
            dist, node = queue.popleft()
            if node in visited: continue
            if node == destination:
                return True
            visited.add(node)
            for neighbor_dist, neighbor in neighbors(maze, node):
                queue.append((dist+neighbor_dist, neighbor))
            
        return False

        
```