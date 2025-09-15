-   https://leetcode.com/problems/swap-nodes-in-pairs/

```python
def swapPairs(self, head: Optional[ListNode]) -> Optional[ListNode]:
    if not head or not head.next:
        return head
    dummy = ListNode()
    dummy.next = head

    prev = dummy
    curr = dummy.next

    while curr and curr.next:
        nxt = curr.next
        curr.next = nxt.next
        nxt.next = curr
        prev.next = nxt

        prev = curr
        curr = curr.next

    return dummy.next
```
