-   https://leetcode.com/problems/longest-substring-with-at-least-k-repeating-characters/description/

```python
def longestSubstring(self, s: str, k: int) -> int:
    n = len(s)
    ans = 0

    def recursiveCheck(word):
        nonlocal ans, k

        count = Counter(word)

        valid = True
        split_char = ""

        for val, freq in count.items():
            if freq < k:
                valid = False
                split_char = val
                break
        if valid:
            ans = max(ans, len(word))
            return
        words = word.split(split_char)
        for wrd in words:
            print(wrd)
            recursiveCheck(wrd)
    recursiveCheck(s)
    return ans
```

```python
def longestSubstring(self, s: str, k: int) -> int:
    n = len(s)
    ans = 0

    for i in range(k,n + 1):
        left, right = 0, i
        count = Counter(s[left:right])
        for val, freq in count.items():
            if freq < k:
                break
        else:
            ans = max(ans, right - left)

        while right < n:
            count[s[right]] += 1
            count[s[left]] -= 1
            if count[s[left]] == 0:
                count.pop(s[left])
            left += 1

            for val, freq in count.items():
                if freq < k:
                    break
            else:
                ans = max(ans, right - left + 1)
            right += 1

    return ans


```
