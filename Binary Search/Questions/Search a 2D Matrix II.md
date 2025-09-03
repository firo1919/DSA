-   https://leetcode.com/problems/search-a-2d-matrix-ii/

```python
def searchMatrix(self, matrix: List[List[int]], target: int) -> bool:
    n, m = len(matrix), len(matrix[0])

    for i in range(n):

        l, h = 0, m - 1
        while l <= h:
            mid = (l + h)//2
            if matrix[i][mid] == target:
                return True
            elif matrix[i][mid] > target:
                h = mid - 1
            else:
                l = mid + 1
    return False
```
