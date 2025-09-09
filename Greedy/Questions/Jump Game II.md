-   https://leetcode.com/problems/jump-game-ii/

```python
def jump(self, nums: List[int]) -> int:
    n = len(nums)
    if n == 1:
        return 0
    ans = 0
    i = 0

    while i < n:
        if i + nums[i] >= n - 1:
            ans += 1
            break
        _max = i + 1
        for j in range(i + 1,i + nums[i] + 1):
            if nums[j]+ j >= nums[_max] + _max:
                _max = j
        i = _max
        ans += 1

    return ans
```
