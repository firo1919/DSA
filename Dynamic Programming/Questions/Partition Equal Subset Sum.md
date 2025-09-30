-   https://leetcode.com/problems/partition-equal-subset-sum/description/

```python
class Solution:
    def canPartition(self, nums: List[int]) -> bool:
        total = sum(nums)
        n = len(nums)
        if total % 2 != 0:
            return False
        target = total // 2
        memo = {}

        def find(_sum, index):
            if (_sum, index) in memo:
                return memo[(_sum, index)]

            if index >= n:
                return False

            if _sum == target:
                return True

            memo[(_sum, index)] = find(_sum, index + 1) or find(_sum + nums[index], index + 1)
            return memo[(_sum, index)]

        return find(0,0)
```
