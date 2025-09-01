-   https://leetcode.com/problems/longest-substring-without-repeating-characters/description/

```python
def lengthOfLongestSubstring(self, s: str) -> int:
    n = len(s)
    left, right = 0, 0
    ans = 0
    count = defaultdict(int)

    while right < n:
        while count[s[right]] >= 1:
            count[s[left]] -= 1
            if count[s[left]] == 0:
                left += 1
        count[s[right]] += 1
        ans = max(ans, right - left + 1)
        right += 1

    return ans
```
