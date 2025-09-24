-   https://leetcode.com/problems/reorder-list/description/

```python
def reorderList(self, head: Optional[ListNode]) -> None:
    right_half = []
    slow = fast = head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
    curr = slow.next
    slow.next = None
    while curr:
        right_half.append(curr)
        curr = curr.next

    curr = head
    while right_half:
        e = right_half.pop()
        l, r = curr, curr.next
        l.next = e
        e.next = r
        curr = r

```
