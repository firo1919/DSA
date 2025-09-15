- https://leetcode.com/problems/reverse-linked-list-ii/description/

```python
def reverseBetween(self, head: Optional[ListNode], left: int, right: int) -> Optional[ListNode]:
    index = 1
    dummy = ListNode()
    dummy.next = head
    curr = dummy.next
    prev = dummy
    start = None
    end = None
    l = None
    r = None
    while curr:
        if index == left:
            start = prev
            l = curr

        if index == right:
            end = curr.next
            r = curr

        if left < index <= right:
            temp = curr.next
            curr.next = prev
            prev = curr
            curr = temp
        else:
            curr = curr.next
            prev = prev.next

        if index > right:
            break
        index += 1
    start.next = r
    l.next = end

    return dummy.next


```
