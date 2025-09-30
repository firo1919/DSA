-   https://leetcode.com/problems/house-robber/

```python
class Solution:
    def rob(self, nums: List[int]) -> int:
        n = len(nums)
        ans = 0
        memo = {}
        def traverse(index):
            if index >= n:
                return 0
            if index not in memo:
                memo[index] = max(traverse(index + 1), nums[index] + traverse(index + 2))

            return memo[index]

        return traverse(0)
```
