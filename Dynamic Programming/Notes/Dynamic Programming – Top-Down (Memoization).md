## 1. Definition / Idea

Dynamic Programming (DP) solves problems by breaking them into **overlapping subproblems** and using previously computed results to avoid recomputation.

- **Top-Down DP = Recursion + Memoization**
    
- Store results of subproblems in a cache (hashmap/array).
    
### Fibonacci Sequence (Motivation)

- Recursive definition:
    
    - `fib(0) = 0`
        
    - `fib(1) = 1`
        
    - `fib(n) = fib(n-1) + fib(n-2)`
        

### Naïve Recursion

```python
def fib(n):
    if n == 0: return 0
    if n == 1: return 1
    return fib(n-1) + fib(n-2)
```

- Time: O(2ⁿ)
    
- Space: O(n) recursion stack
    

### With Memoization

```python
memo = {}
def fib(n):
    if n in memo:
        return memo[n]
    if n == 0 or n == 1:
        return n
    memo[n] = fib(n-1) + fib(n-2)
    return memo[n]
```

- Time: O(n)
    
- Space: O(n)
    

### Key Conditions for DP

- **Optimal Substructure:**  
    The optimal solution to a problem can be built from optimal solutions to its subproblems.
    
- **Overlapping Subproblems:**  
    Same subproblems are solved multiple times in naïve recursion (e.g., Fibonacci).
    

### 2. Common Variants of DP

#### 1. Enumeration Problems

Count the number of distinct ways to achieve a target.

**Example – Climbing Stairs (LC 70):**

```python
def climbStairs(n):
    memo = {}
    def dp(i):
        if i == 1: return 1
        if i == 2: return 2
        if i in memo: return memo[i]
        memo[i] = dp(i-1) + dp(i-2)
        return memo[i]
    return dp(n)
```

---

#### 2. Optimization Problems

Maximize or minimize some value.

**Example – House Robber (LC 198):**

```python
def rob(nums):
    memo = {}
    def dp(i):
        if i < 0: return 0
        if i in memo: return memo[i]
        memo[i] = max(dp(i-1), dp(i-2) + nums[i])
        return memo[i]
    return dp(len(nums)-1)
```

---

#### 3. Yes/No (Decision) Problems

Check whether a condition can be satisfied.

**Example – Partition Equal Subset Sum (LC 416):**

```python
def canPartition(nums):
    total = sum(nums)
    if total % 2: return False
    target = total // 2
    memo = {}
    def dp(i, curr):
        if curr == target: return True
        if i >= len(nums) or curr > target: return False
        if (i, curr) in memo: return memo[(i, curr)]
        memo[(i, curr)] = dp(i+1, curr+nums[i]) or dp(i+1, curr)
        return memo[(i, curr)]
    return dp(0, 0)
```

### 3. Applications of Top-Down DP

- Counting paths (Unique Paths, Climbing Stairs).
    
- Subset/knapsack problems.
    
- Grid-based optimizations (Minimum Path Sum).
    
- Stock trading problems with constraints (transaction fee, cooldown).
    
- Sequence problems (Tribonacci, Target Sum).
    
- Tree-based optimizations (House Robber III).
    