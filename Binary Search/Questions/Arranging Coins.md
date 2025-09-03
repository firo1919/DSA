-   https://leetcode.com/problems/arranging-coins/description/

```python
def arrangeCoins(self, n: int) -> int:
    if n == 1:
        return 1
    l, h = 1, n

    while l <= h:
        mid = (l + h)//2
        coins = (mid)*(mid + 1)//2
        if coins > n:
            h = mid - 1
        else:
            l = mid + 1

    return h
```
