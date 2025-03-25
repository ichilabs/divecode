---
title: "Pacific Atlantic Water Flow"
date: "2025-03-25"
authors:
  - "jathurchan"
featuredVideo: "https://youtu.be/xyfKtV-RVEI"
projects:
  - "52"
---

```python
class Solution:
    def pacificAtlantic(self, heights: List[List[int]]) -> List[List[int]]:
        # input: heights[r][c]
        # output: result[i] = [r, c] where rain water can flow from r, c to Pacific and Atlantic
        # cells where rw can flow to Pacific -> set
        # cells where rw can flow to Atlantic -> set
        # intersection and return a list
        # BFS (Breadth-first search)
        # P: queue = [r=0, c / r, c=0]
        # directions = [(-1, 0), (1, 0), (0, 1), (0, -1)] nr, nc = r+dr, c+dc

        def isValid(r, c):
            return 0 <= r < m and 0 <= c < n

        def canFlowFrom(s, e):
            return heights[s[0]][s[1]] >= heights[e[0]][e[1]]
        
        def cellsReach(queue):  # BFS
            res = set(queue)
            while queue:
                r, c = queue.pop(0)

                for dr, dc in directions:
                    nr, nc = r+dr, c+dc
                    if isValid(nr, nc) and canFlowFrom((nr, nc), (r, c)) and (nr, nc) not in res:
                        res.add((nr, nc))
                        queue.append((nr, nc))
            
            return res

        
        m, n = len(heights), len(heights[0])
        directions = [(-1, 0), (1, 0), (0, 1), (0, -1)]

        pacific, atlantic = [], []

        for r in range(m):
            pacific.append((r, 0))
            atlantic.append((r, n-1))
        
        for c in range(n):
            pacific.append((0, c))
            atlantic.append((m-1, c))

        cellsCanReachPacific = cellsReach(pacific)
        cellsCanReachAtlantic = cellsReach(atlantic)

        return [[r, c] for r,c in cellsCanReachPacific.intersection(cellsCanReachAtlantic)]

        # Time: O(m*n)
        # Space: O(m*n)
```
