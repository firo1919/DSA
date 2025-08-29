-   https://leetcode.com/problems/longest-even-odd-subarray-with-threshold/description/

```python
def longestAlternatingSubarray(self, nums: List[int], threshold: int) -> int:
	n = len(nums)
	left = 0
	max_len = 0

	for right in range(n):
		if nums[right] > threshold:
			left = right + 1
			continue
		if nums[left]%2 != 0:
			left += 1
			continue
		if right > left and nums[right]%2 == nums[right - 1]%2:
			left = right
			continue

		max_len = max(max_len, right - left + 1)

	return max_len
```
