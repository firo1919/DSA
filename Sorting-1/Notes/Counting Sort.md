## 1. Definition / Idea

Counting Sort is a **distribution-based** algorithm that sorts integers by counting the number of occurrences of each unique value. It then reconstructs the sorted array using this frequency information.

## 2. Key Properties

- **Time Complexity:**
    
    - Best case: Ω(n + k)
        
    - Average case: Θ(n + k)
        
    - Worst case: O(n + k)
        
    - _n = number of elements, k = range of input values_
        
- **Space Complexity:** O(n + k)
    
- **Stable:** Yes (if implemented carefully)
    
- **In-Place:** No (requires extra arrays)
    

## 3. Steps / Working

1. Find the minimum and maximum values in the array.
    
2. Create a counting array of size `(max - min + 1)`.
    
3. Count occurrences of each element.
    
4. Reconstruct the sorted array using the counts.
    
5. If stability is required, compute prefix sums in the count array and place elements in output accordingly.
    

## 6. Example (Python)

```python
def counting_sort(arr):
    # Handle empty input
    if not arr:
        return arr
    
    # Find range of input values
    minimum = min(arr)
    maximum = max(arr)

    # Initialize count array with zeros
    count = [0] * (maximum - minimum + 1)

    # Count each element’s frequency
    for num in arr:
        count[num - minimum] += 1

    # Reconstruct sorted array
    index = 0
    for i in range(len(count)):
        while count[i] > 0:
            arr[index] = i + minimum
            index += 1
            count[i] -= 1

    return arr
```

## 7. Use Cases

- Sorting integers when the range of values is not much larger than `n`.
    
- Efficient for problems like frequency sorting or ranking.
    
- Often used as a subroutine in **Radix Sort**.
    

## 6. Variations / Related Concepts

- Can be adapted to handle negative numbers by offsetting indices.
    
- Related: Bucket Sort, Radix Sort (other distribution-based algorithms).
    

## 7. Common Mistakes & Pitfalls

- Using Counting Sort when the range `k` is too large → excessive memory usage.
    
- Forgetting to offset indices when negatives are present.
    
- Incorrect reconstruction if prefix sums (for stable version) aren’t used.
    