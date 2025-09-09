-   https://leetcode.com/problems/minimum-number-of-arrows-to-burst-balloons/description/

```python
def findMinArrowShots(self, points: List[List[int]]) -> int:
    if len(points) == 1:
        return 1
    points.sort(key = lambda a: a[0])
    arrows = 0
    l, h = points[0][0], points[0][1]
    for s, e in points:
        if s <= h:
            l = max(l, s)
            h = min(h, e)
        else:
            arrows += 1
            l, h = s, e

    return arrows + 1
```
