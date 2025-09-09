-   https://leetcode.com/problems/lemonade-change/

```python
def lemonadeChange(self, bills: List[int]) -> bool:
    bill_deno = {10: 0, 5: 0}

    for bill in bills:
        if bill == 5:
            bill_deno[5] += 1
        elif bill == 10:
            if bill_deno[5] > 0:
                bill_deno[5] -= 1
                bill_deno[10] += 1
            else:
                return False
        elif bill == 20:
            if bill_deno[10] > 0:
                bill_deno[10] -= 1
                bill -= 10
            elif bill_deno[5] >= 2:
                bill_deno[5] -= 2
                bill -= 10
            if bill_deno[5] > 0:
                bill_deno[5] -= 1
                bill -= 5
            if bill != 5:
                return False

    return True
```
