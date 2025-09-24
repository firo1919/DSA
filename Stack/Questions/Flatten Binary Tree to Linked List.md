-   https://leetcode.com/problems/flatten-binary-tree-to-linked-list/description/

```python
def flatten(self, root: Optional[TreeNode]) -> None:
    if not root:
        return root
    stack = [root]
    p = ListNode()
    while stack:
        e = stack.pop()
        l, r = e.left, e.right
        if r:
            stack.append(r)
        if l:
            stack.append(l)
        p.right = e
        p.left = None
        p = p.right
```
