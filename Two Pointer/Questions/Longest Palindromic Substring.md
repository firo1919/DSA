-   https://leetcode.com/problems/longest-palindromic-substring/

```python
def longestPalindrome(self, s: str) -> str:
        n = len(s)
        start, end = 0, 0
        for i in range(n):
            j, k = i, i
            while j >= 0 and k < n and s[j] == s[k]:
                length = k - j + 1
                if length > end - start + 1:
                    start = j
                    end = k
                j -= 1
                k += 1

            j, k = i, i + 1
            while j >= 0 and k < n and s[j] == s[k]:
                length = k - j + 1
                if length > end - start + 1:
                    start = j
                    end = k
                j -= 1
                k += 1

        return s[start:end + 1]
```
