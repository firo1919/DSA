-   https://leetcode.com/problems/minimum-number-of-days-to-make-m-bouquets/

```python
def minDays(self, bloomDay: List[int], m: int, k: int) -> int:
    max_duration = max(bloomDay)
    n = len(bloomDay)
    l, h = 0, max_duration

    def valid(duration):
        c = 0
        left, right = 0, 0
        while right < n:
            if bloomDay[right] > duration:
                left = right + 1
            elif right - left + 1 == k:
                c += 1
                left = right + 1
            right += 1
        return c >= m

    while l <= h:
        mid = (l + h)//2
        if valid(mid):
            h = mid - 1
        else:
            l = mid + 1

    if l > max_duration:
        return -1
    return l
```
