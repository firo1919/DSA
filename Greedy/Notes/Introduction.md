## 2. Definition / Idea

A **greedy algorithm** builds up a solution step by step, making the **locally optimal choice** at each stage, with the hope that these choices lead to a global optimum.

## 3. Key Properties

- **Greedy Choice Property** – At each step, choose the best available option without reconsidering.
    
- **Optimal Substructure** – An optimal solution to the whole problem can be constructed from optimal solutions of subproblems.
    

---

# 📘 DSA Notes

## 1. Topic

**Motivating Problem – Coin Collector’s Dilemma**

- You have `N` dollars to make using given coin denominations.
    
- Use the fewest number of coins possible.
    

### Example

Target: `87` with coins `{25, 10, 5, 1}`

- Feasible Solution 1: `87 × 1` → ❌ not minimal
    
- Feasible Solution 2: `8 × 10 + 7 × 1` → ❌ not minimal
    
- Optimal Solution: `{25, 25, 25, 10, 1, 1}` → ✅ 6 coins
    

---

# 📘 DSA Notes

## 1. Topic

**Optimization Problems**

- **Definition:** Problems where the goal is to find the _best_ solution among feasible ones.
    
- **Components:**
    
    1. **Objective Function** – Minimize or maximize something (e.g., minimize coins).
        
    2. **Decision Variables** – Choices that affect the outcome (e.g., coin denominations used).
        
    3. **Constraints** – Restrictions (e.g., sum of coins = N).
        

---

# 📘 DSA Notes

## 1. Topic

**Greedy Terms**

- **Subproblem** – A smaller instance of the original problem.
    
- **Local Optimum** – Best choice in the current step.
    
- **Global Optimum** – Best solution overall.
    
- **Selection Rule** – Guides which option to choose next.
    
- **Heuristic** – Practical rule/shortcut for making choices efficiently.
    
- **Termination Condition** – When to stop the algorithm (e.g., when target is reached).
    

---

# 📘 DSA Notes

## 1. Topic

**Greedy Example – Heuristic**

- Problem: Give change for N using coin denominations.
    
- Heuristic: Always pick the largest coin ≤ remaining amount.
    

✅ Works for `{25, 10, 5, 1}`  
❌ Fails for `{1, 3, 4}`, target `6`

- Greedy → `{4, 1, 1}` (3 coins)
    
- Optimal → `{3, 3}` (2 coins)
    

⚠️ Lesson: **Greedy doesn’t always guarantee global optimum.**

---

# 📘 DSA Notes

## 1. Topic

**Activity Selection Problem**

- **Problem:** Maximize the number of non-overlapping activities.
    
- **Approach:** Always pick the activity that finishes earliest.
    

### Greedy Algorithm

1. Sort activities by finish time.
    
2. Pick the first activity.
    
3. For each subsequent activity, if its start ≥ last finish, select it.
    

### Correctness Proof

- **Base Case:** First chosen activity can always be swapped into an optimal solution.
    
- **Inductive Step:** Assume optimality up to step k. The k+1 greedy choice still leads to optimal solution (exchange argument).
    

---

# 📘 DSA Notes

## 1. Topic

**Proof Techniques for Greedy Algorithms**

1. **Proof by Induction** – Show correctness for base case and inductive step.
    
2. **Proof by Contradiction** – Assume greedy fails, derive contradiction.
    
3. **Exchange Argument** – Show any optimal solution can be transformed into greedy solution without loss.
    

---

# 📘 DSA Notes

## 1. Topic

**Greedy Pitfalls & Weaknesses**

1. Greedy choice may not lead to global optimum.
    
2. Ignores future consequences.
    
3. Often depends on correct sorting.
    
4. Proof of correctness can be difficult.
    

---

# 📘 DSA Notes

## 1. Topic

**Greedy Problems to Practice**

- [Lemonade Change](https://leetcode.com/problems/lemonade-change/)
    
- [Minimum Arrows to Burst Balloons](https://leetcode.com/problems/minimum-number-of-arrows-to-burst-balloons/)
    
- [Rabbits in Forest](https://leetcode.com/problems/rabbits-in-forest/)
    
- [Minimum Moves to Reach Target Score](https://leetcode.com/problems/minimum-moves-to-reach-target-score/)
    
- [Minimum Replacements to Sort the Array](https://leetcode.com/problems/minimum-replacements-to-sort-the-array/description/)
    
- [Patching Array](https://leetcode.com/problems/patching-array/)
    
- [Largest Perimeter Triangle](https://leetcode.com/problems/largest-perimeter-triangle/)
    
- [Jump Game](https://leetcode.com/problems/jump-game/)
    
- [Two City Scheduling](https://leetcode.com/problems/two-city-scheduling/)
    

---

# 📘 DSA Notes

## 1. Topic

**Quote of the Day**

> “A problem well stated is a problem half solved.” – _John Dewey_

---

✅ That completes the **Greedy Algorithms** lecture notes:

- Coin Collector’s Dilemma (motivation)
    
- Optimization problem basics
    
- Greedy terms and heuristics
    
- Coin system example (works/fails)
    
- Activity Selection Problem + Proof
    
- Pitfalls of greedy methods
    
- Practice problems
    

Would you like me to also prepare a **cheat sheet of greedy strategies** (coin change, interval scheduling, Huffman coding, Kruskal’s MST, etc.), or keep these strictly lecture-based?