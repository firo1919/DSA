- https://leetcode.com/problems/3sum/description/
```python
def threeSum(self, nums: List[int]) -> List[List[int]]:
        n = len(nums)
        result = []
        nums.sort()
        for i in range(n):
            if i > 0 and nums[i] == nums[i - 1]:
                continue

            target = -nums[i]
            j, k = i + 1, n - 1
            while j < k:
                _sum = nums[j] + nums[k]
                if _sum > target:
                    k -= 1
                elif _sum < target:
                    j += 1
                else:
                    result.append([nums[i], nums[j], nums[k]])
                    k -= 1
                    j += 1
                    while j < k and nums[j] == nums[j - 1]:
                        j += 1

        return result
```
