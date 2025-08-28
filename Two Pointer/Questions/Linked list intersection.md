-   https://leetcode.com/problems/intersection-of-two-linked-lists/description/

```python
def getIntersectionNode(self, headA: ListNode, headB: ListNode) -> Optional[ListNode]:

	n ,m = 0, 0
	temp1 = headA
	temp2 = headB

	while temp1:
		n += 1
		temp1 = temp1.next

	while temp2:
		m += 1
		temp2 = temp2.next

	while n > m:
		headA = headA.next
		n -= 1

	while m > n:
		headB = headB.next
		m -= 1

	while headA and headB:
		if headA == headB:
		return headA

	headA = headA.next
	headB = headB.next

	return None
```
