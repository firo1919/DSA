-   https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/

```python
def strStr(self, haystack: str, needle: str) -> int:

	j = 0
	for i in range(len(haystack)):
		while j - i + 1 < len(needle) and j < len(haystack):
		j += 1
		if haystack[i: j + 1] == needle:
			return i

	return -1
```
