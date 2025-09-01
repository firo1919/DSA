-   https://leetcode.com/problems/arithmetic-slices/

```python
def numberOfArithmeticSlices(self, nums: List[int]) -> int:
        curr = 0
        count = 0
        n = len(nums)

        for i in range(2, n):
            if nums[i] - nums[i - 1] == nums[i - 1] - nums[i - 2]:
                curr += 1
                count += curr
            else:
                curr = 0

        return count
```

```python
def numberOfArithmeticSlices(self, nums: List[int]) -> int:
        difference = [0]
        n = len(nums)
        count = 0

        for i in range(1, n):
            difference.append(nums[i - 1] - nums[i])
        left, right = 1, 1
        while right < n:
            if difference[right] != difference[left]:
                left = right
            if right - left + 2 >= 3:
                count += (right - left + 2) - 2
            right += 1

        return count
```
