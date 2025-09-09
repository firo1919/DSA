-   https://leetcode.com/problems/rabbits-in-forest/

```python
def numRabbits(self, answers: List[int]) -> int:
    rabbit_count = Counter(answers)
    ans = 0

    for val, freq in rabbit_count.items():
        if freq <= val + 1:
            ans += val + 1
        else:
            ans += math.ceil(freq/(val + 1))*(val + 1)

    return ans
```
