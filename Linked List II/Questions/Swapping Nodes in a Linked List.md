-   https://leetcode.com/problems/swapping-nodes-in-a-linked-list/description/

```python
def swapNodes(self, head: Optional[ListNode], k: int) -> Optional[ListNode]:
    left = right = head
    index = 1
    frLeft = left
    while right.next:
        if index >= k:
            if index == k:
                frLeft = right
            left = left.next
        right = right.next
        index += 1
    if index == k:
        frLeft = right
    val = left.val
    left.val = frLeft.val
    frLeft.val = val
    return head

```
