- https://leetcode.com/problems/random-point-in-non-overlapping-rectangles/description/

```python
class Solution:

    def __init__(self, rects: List[List[int]]):
        self.rects = rects
        areas = []
        self.area_prefix_sum = []
        for a, b, c, d in rects:
            areas.append((c - a + 1)*(d - b + 1))

        total = 0
        for area in areas:
            total += area
            self.area_prefix_sum.append(total)


    def pick(self) -> List[int]:
        index = random.randrange(0, self.area_prefix_sum[-1] - 1)
        l, h = 0, len(self.area_prefix_sum) - 1
        while l < h:
            mid = (l + h)//2
            if self.area_prefix_sum[mid] > index:
                h = mid
            else:
                l = mid + 1
        x = random.randrange(self.rects[h][0], self.rects[h][2] + 1)
        y = random.randrange(self.rects[h][1], self.rects[h][3] + 1)
        return [x, y]
```
