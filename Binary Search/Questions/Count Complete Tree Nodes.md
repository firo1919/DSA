-https://leetcode.com/problems/count-complete-tree-nodes/description/

```python
def countNodes(self, root: Optional[TreeNode]) -> int:
    if not root:
        return 0
    def exists(index, height, node):
        mask = 1<<(height - 2)
        while mask and node:
            if index & mask:
                node = node.right
            else:
                node = node.left
            mask >>= 1
        if node:
            return True

        return False


    h = 0
    left_tree = root
    while left_tree:
        h += 1
        left_tree = left_tree.left

    if h == 1:
        return 1
    l, r = 0, 2**(h - 1) - 1

    while l <= r:
        mid = (l + r)//2
        if exists(mid, h, root):
            l = mid + 1
        else:
            r = mid - 1

    return l + 2**(h - 1) - 1
```
