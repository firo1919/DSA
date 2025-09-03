## 2. Problem

Given a singly linked list, remove the n-th node from the end.  
[Leetcode 19](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)

## 3. Approaches

### Approach I – Two Pass

1. Count total nodes `k`.
    
2. Find `(k-n)`th node.
    
3. Remove the next node.
    

### Approach II – One Pass (Two Pointers)

1. Move `ahead` pointer `n` steps forward.
    
2. Start `behind` from head.
    
3. Move both until `ahead` reaches end.
    
4. `behind` now points to the target node.
    

## 4. Example (Python)

```python
def removeNthFromEnd(head, n):
    dummy = ListNode(0, head)
    ahead = behind = dummy

    # Move ahead n+1 steps
    for _ in range(n+1):
        ahead = ahead.next

    # Move both pointers
    while ahead:
        ahead = ahead.next
        behind = behind.next

    # Remove node
    behind.next = behind.next.next
    return dummy.next
```

---

# 📘 DSA Notes

## 1. Topic

**Find Middle of Linked List**

## 2. Problem

Return the middle node of a singly linked list.  
[Leetcode 876](https://leetcode.com/problems/middle-of-the-linked-list/)

## 3. Approach – Fast and Slow Pointers

- `slow` moves one step.
    
- `fast` moves two steps.
    
- When `fast` reaches end, `slow` is at middle.
    

## 4. Example (Python)

```python
def middleNode(head):
    slow = fast = head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
    return slow
```

---

# 📘 DSA Notes

## 1. Topic

**Floyd’s Cycle Detection (Tortoise & Hare)**

## 2. Problem

Detect if a linked list has a cycle and return the node where it begins.  
[Leetcode 142](https://leetcode.com/problems/linked-list-cycle-ii/)

## 3. Approach

- **Phase I – Cycle Detection**
    
    - `slow` moves one step, `fast` moves two steps.
        
    - If they meet, a cycle exists.
        
- **Phase II – Find Cycle Entrance**
    
    - Reset `slow` to head.
        
    - Move both `slow` and `fast` one step at a time.
        
    - They meet at the cycle start.
        

## 4. Example (Python)

```python
def detectCycle(head):
    slow = fast = head
    
    # Phase I: detect cycle
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        if slow == fast:
            break
    else:
        return None
    
    # Phase II: find entrance
    slow = head
    while slow != fast:
        slow = slow.next
        fast = fast.next
    return slow
```

---

# 📘 DSA Notes

## 1. Topic

**Common Pitfalls in Linked Lists**

- **Null Pointer Errors**
    
    - Always check if `head` or `head.next` is `None` before accessing.
        
- **Losing Reference to Head**
    
    - If modifying list, store head in a variable and return it.
        
- **Wrong Loop Conditions**
    
    - Example: Using `while fast:` instead of `while fast and fast.next:` in middle node problem.
        
- **Example Fix**
    

```python
def containsTarget(head, target):
    while head and head.val != target:  # must check head first
        head = head.next
    return head is not None
```

---

# 📘 DSA Notes

## 1. Topic

**Practice Questions**

- [Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/)
    
- [Palindrome Linked List](https://leetcode.com/problems/palindrome-linked-list/)
    
- [Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/)
    
- [Remove Duplicates from Sorted List](https://leetcode.com/problems/remove-duplicates-from-sorted-list/)
    
- [Partition List](https://leetcode.com/problems/partition-list/)
    
- [Linked List Cycle II](https://leetcode.com/problems/linked-list-cycle-ii/)
    
- [LRU Cache](https://leetcode.com/problems/lru-cache/)
    
- [Delete Node in a Linked List](https://leetcode.com/problems/delete-node-in-a-linked-list/)
    

---

# 📘 DSA Notes

## 1. Topic

**Complexity of Linked List II Problems**

- **Remove N-th Node from End:** O(n)
    
- **Middle Node:** O(n)
    
- **Cycle Detection (Floyd’s):** O(n) time, O(1) space
    
- **Reverse List:** O(n)
    
- **Merge Lists:** O(n+m)
    

---

✅ That completes the **Linked List II** lecture:

- Remove N-th Node from End
    
- Middle Node
    
- Floyd’s Cycle Detection
    
- Common Pitfalls
    
- Practice Problems
    
- Complexity
    

Do you want me to merge **Linked List I & II notes into a single “Linked List Master Note”** for quick revision, or keep them separate?