-   https://leetcode.com/problems/search-in-rotated-sorted-array-ii/

```python
def search(self, nums: List[int], target: int) -> bool:
    l1, h1 = 0, 0
    n = len(nums)

    for i in range(n):
        if i > 0 and nums[i] < nums[i - 1]:
            h1 = i - 1
            break
    l2, h2 = h1 + 1, n - 1

    while l1 <= h1:
        mid = (l1 + h1)//2
        if nums[mid] == target:
            return True
        elif nums[mid] > target:
            h1 = mid - 1
        else:
            l1 = mid + 1

    while l2 <= h2:
        mid = (l2 + h2)//2
        if nums[mid] == target:
            return True
        elif nums[mid] > target:
            h2 = mid - 1
        else:
            l2 = mid + 1

    return False
```
