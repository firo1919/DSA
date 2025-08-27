## 1. Definition / Idea

Bubble Sort repeatedly compares adjacent elements and swaps them if they are in the wrong order. After each pass, the largest element “bubbles up” to its correct position at the end.

## 2. Key Properties

- **Time Complexity:**
    
    - Best case: Ω(n) (already sorted)
        
    - Average case: Θ(n²)
        
    - Worst case: O(n²)
        
- **Space Complexity:** O(1)
    
- **Stable:** Yes
    
- **In-Place:** Yes
    

## 3. Steps / Working

1. Iterate through the array from left to right.
    
2. Compare each pair of adjacent elements.
    
3. Swap them if they are in the wrong order.
    
4. After one pass, the largest element is at the end.
    
5. Repeat until no swaps are needed.
    

## 4. Example (Python)

```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        swapped = False  # Track if any swap happens in this pass

        # Last i elements are already in correct position
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1]:
                # Swap adjacent elements if they are in the wrong order
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
                swapped = True

        # If no swaps, array is already sorted → break early
        if not swapped:
            break
    return arr
```

## 5. Use Cases

- Teaching sorting fundamentals.
    
- Sorting very small datasets.
    
- Avoid in large-scale applications due to inefficiency.
    

## 6. Variations / Related Concepts

- **Optimized Bubble Sort:** Early exit check (`swapped`).
    
- Related: Selection Sort, Insertion Sort (basic comparison sorts).
    

## 7. Common Mistakes & Pitfalls

- Forgetting to reduce the inner loop range after each pass.
    
- Missing the early exit condition → causes unnecessary passes.
    
- Using Bubble Sort in real-world apps instead of efficient O(n log n) algorithms.
    
