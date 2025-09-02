-   https://leetcode.com/problems/random-pick-with-weight/description/

```python
class Solution:

    def __init__(self, w: List[int]):
        self.weight_prefix = []
        total = 0
        for weight in w:
            total += weight
            self.weight_prefix.append(total)


    def pickIndex(self) -> int:
        index = random.randrange(1, self.weight_prefix[-1] + 1)
        l, h = 0, len(self.weight_prefix) - 1

        while l < h:
            mid = (l + h)//2
            if self.weight_prefix[mid] >= index:
                h = mid
            else:
                l = mid + 1

        return h
```
