- https://leetcode.com/problems/populating-next-right-pointers-in-each-node/description/

```python
def connect(self, root: 'Optional[Node]') -> 'Optional[Node]':
    if not root:
        return root
    queue = deque([root])

    while queue:
        e = queue.popleft()

        if e.left:
            e.left.next = e.right
            queue.append(e.left)
        if e.right:
            if e.next:
                e.right.next = e.next.left
            queue.append(e.right)

    return root

```
