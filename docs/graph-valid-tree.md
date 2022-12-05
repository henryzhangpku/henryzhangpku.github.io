---
id: graph-valid-tree
title: Graph Valid Tree
sidebar_label: Graph Valid Tree
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class Solution(object):
    def validTree(self, n, edges):
        # A structure to track each node's [visited_from, neighbors]
        visited_from = [-1] * n
        neighbors = collections.defaultdict(list)
        for u, v in edges:
            neighbors[u].append(v)
            neighbors[v].append(u)

        # BFS to check whether the graph is valid tree.
        visited = {}
        q = collections.deque([0])
        while q:
            i = q.popleft()
            visited[i] = True
            for node in neighbors[i]:
                if node != visited_from[i]:
                    if node in visited:
                        return False
                    else:
                        visited[node] = True
                        visited_from[node] = i
                        q.append(node)
        return len(visited) == n
        
```