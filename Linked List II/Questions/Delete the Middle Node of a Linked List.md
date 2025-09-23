-   https://leetcode.com/problems/delete-the-middle-node-of-a-linked-list/description/

```python
def deleteMiddle(self, head: Optional[ListNode]) -> Optional[ListNode]:
    dummy = ListNode()
    dummy.next = head
    prev = dummy
    slow = fast = dummy.next

    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        prev = prev.next

    prev.next = prev.next.next
    return dummy.next
```
