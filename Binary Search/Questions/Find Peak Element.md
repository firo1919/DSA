-   https://leetcode.com/problems/find-peak-element/

```python
def findPeakElement(self, nums: List[int]) -> int:
    n = len(nums)
    l, h = 0, n - 1

    while l <= h:
        mid = (l + h)//2
        if (mid - 1 == -1 or nums[mid] > nums[mid - 1]) and (mid + 1 == n or nums[mid] > nums[mid + 1]):
            return mid
        elif mid - 1 == -1:
            l = mid + 1
        elif mid + 1 == n:
            h = mid - 1
        elif nums[mid - 1] > nums[mid + 1]:
            h = mid - 1
        else:
            l = mid + 1
    return -1
```
