-   https://leetcode.com/problems/remove-nodes-from-linked-list/description/

```python
def removeNodes(self, head: Optional[ListNode]) -> Optional[ListNode]:
    stack = []
    curr = head

    while curr:
        while stack and stack[-1].val < curr.val:
            stack.pop()
        stack.append(curr)
        curr = curr.next

    l = stack[0]
    for i in range(1, len(stack)):
        l.next = stack[i]
        l = l.next
    l.next = None
    return stack[0]
```
