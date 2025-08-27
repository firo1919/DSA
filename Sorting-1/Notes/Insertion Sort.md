## 1. Definition / Idea

Insertion Sort builds a sorted portion of the array one element at a time. Each new element is inserted into its correct position within the already-sorted part.

## 2. Key Properties

- **Time Complexity:**
    
    - Best case: Ω(n) (already sorted)
        
    - Average case: Θ(n²)
        
    - Worst case: O(n²)
        
- **Space Complexity:** O(1)
    
- **Stable:** Yes
    
- **In-Place:** Yes
    

## 3. Steps / Working

1. Treat the first element as sorted.
    
2. Pick the next element.
    
3. Compare it with elements in the sorted portion (moving left).
    
4. Shift larger elements one step right.
    
5. Insert the current element in its correct position.
    
6. Repeat until all elements are sorted.
    

## 4. Example (Python)

```python
def insertion_sort(arr):
    n = len(arr)
    for i in range(1, n):
        key = arr[i]  # Current element to be placed
        j = i - 1

        # Shift elements greater than key to the right
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1

        # Insert the key into its correct position
        arr[j + 1] = key

    return arr
```

## 5. Use Cases

- Efficient for small datasets.
    
- Works well for nearly sorted arrays (best case O(n)).
    
- Commonly used in practice for small helper sorts inside more complex algorithms.
    

## 6. Variations / Related Concepts

- Binary Insertion Sort (uses binary search for finding position).
    
- Related: Bubble Sort, Selection Sort.
    

## 7. Common Mistakes & Pitfalls

- Forgetting to shift elements properly before inserting the key.
    
- Confusing it with Selection Sort — Insertion shifts elements, Selection swaps.
    
- Poor performance for large, random datasets.
    