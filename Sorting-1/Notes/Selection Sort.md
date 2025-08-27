## 1. Definition / Idea

Selection Sort repeatedly selects the smallest element from the unsorted portion of the list and places it at the beginning. This process continues until the entire list is sorted.

## 2. Key Properties

- **Time Complexity:**
    
    - Best case: Ω(n²)
        
    - Average case: Θ(n²)
        
    - Worst case: O(n²)
        
- **Space Complexity:** O(1)
    
- **Stable:** No
    
- **In-Place:** Yes
    

## 3. Steps / Working

1. Start with the first index as the minimum.
    
2. Find the smallest element in the unsorted portion.
    
3. Swap it with the element at the current index.
    
4. Move the boundary between sorted and unsorted parts forward.
    
5. Repeat until all elements are sorted.
    

## 4. Example (Python)

```python
def selection_sort(arr):
    n = len(arr)
    for i in range(n):
        # Assume the first element of unsorted part is the minimum
        min_index = i

        # Find the smallest element in the unsorted portion
        for j in range(i + 1, n):
            if arr[j] < arr[min_index]:
                min_index = j

        # Swap the found minimum element with the first element
        arr[i], arr[min_index] = arr[min_index], arr[i]

    return arr
```

## 5. Use Cases

- Simple implementation for small datasets.
    
- Useful when memory space is very limited (constant space).
    
- Good for learning sorting logic fundamentals.
    

## 6. Variations / Related Concepts

- Can be modified to select the largest element and place it at the end.
    
- Related algorithms: Bubble Sort, Insertion Sort.
    

## 7. Common Mistakes & Pitfalls

- Assuming it’s stable (it is **not**, because swaps may change the relative order).
    
- Forgetting that every iteration requires scanning the rest of the list → always O(n²).
    
- Inefficient for large inputs compared to Merge Sort or Quick Sort.
    
