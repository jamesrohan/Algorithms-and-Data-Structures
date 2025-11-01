<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [🔄 Dynamic Programming Pattern - Complete Interview Guide](#-dynamic-programming-pattern---complete-interview-guide)
  - [1️⃣ **Pattern Overview**](#1️⃣-pattern-overview)
    - [🎯 Core Concept](#-core-concept)
    - [🎪 When to Use This Pattern](#-when-to-use-this-pattern)
    - [⏱️ Complexity Overview](#️-complexity-overview)
  - [2️⃣ **Pattern Recognition \& Detection**](#2️⃣-pattern-recognition--detection)
    - [🔍 Key Problem Signals](#-key-problem-signals)
    - [🎨 Visual Pattern Recognition](#-visual-pattern-recognition)
    - [📊 The Two Pillars of DP](#-the-two-pillars-of-dp)
    - [🎭 DP Recognition Flowchart](#-dp-recognition-flowchart)
    - [🎪 Common DP Patterns](#-common-dp-patterns)
  - [3️⃣ **Standard Algorithm Templates**](#3️⃣-standard-algorithm-templates)
    - [🎯 Template 1: Top-Down (Memoization)](#-template-1-top-down-memoization)
    - [📊 Template 2: Bottom-Up (Tabulation)](#-template-2-bottom-up-tabulation)
    - [🎯 Template 3: 2D DP](#-template-3-2d-dp)
    - [💾 Template 4: Space-Optimized DP](#-template-4-space-optimized-dp)
  - [4️⃣ **Common Interview Problem Types**](#4️⃣-common-interview-problem-types)
    - [🎯 Essential Problems Every Candidate Should Know](#-essential-problems-every-candidate-should-know)
  - [5️⃣ **Advanced Techniques \& Variations**](#5️⃣-advanced-techniques--variations)
  - [🔬 Technique 1: Linear DP (1D Problems)](#-technique-1-linear-dp-1d-problems)
    - [📋 When to Use](#-when-to-use)
    - [🎯 Core Implementation Pattern](#-core-implementation-pattern)
    - [📊 Visual Walkthrough](#-visual-walkthrough)
    - [💻 Complete Problem Solutions](#-complete-problem-solutions)
      - [**Problem 1: Climbing Stairs (LC 70)**](#problem-1-climbing-stairs-lc-70)
      - [**Problem 2: House Robber (LC 198)**](#problem-2-house-robber-lc-198)
      - [**Problem 3: Decode Ways (LC 91)**](#problem-3-decode-ways-lc-91)
      - [**Problem 4: Min Cost Climbing Stairs (LC 746)**](#problem-4-min-cost-climbing-stairs-lc-746)
    - [🎯 Linear DP Problem List](#-linear-dp-problem-list)
  - [🔬 Technique 2: Knapsack DP (0/1 \& Unbounded)](#-technique-2-knapsack-dp-01--unbounded)
    - [📋 When to Use](#-when-to-use-1)
    - [🎯 Core Implementation - 0/1 Knapsack](#-core-implementation---01-knapsack)
    - [🎯 Core Implementation - Unbounded Knapsack](#-core-implementation---unbounded-knapsack)
    - [📊 Visual Walkthrough - 0/1 Knapsack](#-visual-walkthrough---01-knapsack)
    - [💻 Complete Problem Solutions](#-complete-problem-solutions-1)
      - [**Problem 1: Partition Equal Subset Sum (LC 416)**](#problem-1-partition-equal-subset-sum-lc-416)
      - [**Problem 2: Coin Change (LC 322)**](#problem-2-coin-change-lc-322)
      - [**Problem 3: Target Sum (LC 494)**](#problem-3-target-sum-lc-494)
      - [**Problem 4: Ones and Zeroes (LC 474)**](#problem-4-ones-and-zeroes-lc-474)
    - [🎯 Knapsack DP Problem List](#-knapsack-dp-problem-list)
  - [🔬 Technique 3: Longest Common Subsequence (LCS) Pattern](#-technique-3-longest-common-subsequence-lcs-pattern)
    - [📋 When to Use](#-when-to-use-2)
    - [🎯 Core Implementation](#-core-implementation)
    - [📊 Visual Walkthrough](#-visual-walkthrough-1)
    - [💻 Complete Problem Solutions](#-complete-problem-solutions-2)
      - [**Problem 1: Longest Common Subsequence (LC 1143)**](#problem-1-longest-common-subsequence-lc-1143)
      - [**Problem 2: Edit Distance (LC 72)**](#problem-2-edit-distance-lc-72)
      - [**Problem 3: Delete Operation for Two Strings (LC 583)**](#problem-3-delete-operation-for-two-strings-lc-583)
      - [**Problem 4: Shortest Common Supersequence (LC 1092)**](#problem-4-shortest-common-supersequence-lc-1092)
    - [🎯 LCS Pattern Problem List](#-lcs-pattern-problem-list)
  - [🔬 Technique 4: Grid Path DP (2D)](#-technique-4-grid-path-dp-2d)
    - [📋 When to Use](#-when-to-use-3)
    - [🎯 Core Implementation](#-core-implementation-1)
    - [📊 Visual Walkthrough](#-visual-walkthrough-2)
    - [💻 Complete Problem Solutions](#-complete-problem-solutions-3)
      - [**Problem 1: Unique Paths (LC 62)**](#problem-1-unique-paths-lc-62)
      - [**Problem 2: Minimum Path Sum (LC 64)**](#problem-2-minimum-path-sum-lc-64)
      - [**Problem 3: Unique Paths II (LC 63)**](#problem-3-unique-paths-ii-lc-63)
      - [**Problem 4: Dungeon Game (LC 174)**](#problem-4-dungeon-game-lc-174)
    - [🎯 Grid Path DP Problem List](#-grid-path-dp-problem-list)
  - [6️⃣ **Comprehensive Comparison Table**](#6️⃣-comprehensive-comparison-table)
  - [7️⃣ **Problem-to-Approach Mapping**](#7️⃣-problem-to-approach-mapping)
  - [8️⃣ **Performance Characteristics**](#8️⃣-performance-characteristics)
  - [9️⃣ **Selection Decision Tree**](#9️⃣-selection-decision-tree)
  - [🔟 **Common Pitfalls Analysis**](#-common-pitfalls-analysis)
    - [🚨 Critical Bug Example: Wrong Base Case in Fibonacci](#-critical-bug-example-wrong-base-case-in-fibonacci)
      - [❌ WRONG CODE (with bugs):](#-wrong-code-with-bugs)
    - [📊 Execution Trace - WRONG vs EXPECTED:](#-execution-trace---wrong-vs-expected)
    - [🔬 Detailed Bug Breakdown:](#-detailed-bug-breakdown)
    - [✅ CORRECT CODE Comparison:](#-correct-code-comparison)
    - [🚨 Another Common Bug: 2D DP Index Confusion](#-another-common-bug-2d-dp-index-confusion)
      - [❌ WRONG CODE:](#-wrong-code)
    - [🎯 Key Takeaways from Bug Analysis:](#-key-takeaways-from-bug-analysis)
  - [1️⃣1️⃣ **Interview Success Tips**](#1️⃣1️⃣-interview-success-tips)
    - [🎯 Problem Recognition Signals](#-problem-recognition-signals)
    - [🎪 Optimization Strategy Table](#-optimization-strategy-table)
    - [🚨 Common Edge Cases with Code Examples](#-common-edge-cases-with-code-examples)
      - [**1️⃣ Empty or Single Element Input**](#1️⃣-empty-or-single-element-input)
      - [**2️⃣ Negative Numbers**](#2️⃣-negative-numbers)
      - [**3️⃣ Integer Overflow (Less Common in Python)**](#3️⃣-integer-overflow-less-common-in-python)
      - [**4️⃣ 2D Grid Out of Bounds**](#4️⃣-2d-grid-out-of-bounds)
      - [**5️⃣ String Index Misalignment**](#5️⃣-string-index-misalignment)
    - [✅ Interview Debug Checklist](#-interview-debug-checklist)
    - [💡 Interview Communication Framework](#-interview-communication-framework)
    - [🎯 Pattern-Specific Red Flags](#-pattern-specific-red-flags)
  - [1️⃣2️⃣ **ASCII Problem Solving Flow**](#1️⃣2️⃣-ascii-problem-solving-flow)
    - [🎯 Sample Problem: House Robber](#-sample-problem-house-robber)
    - [🎭 Sample Problem 2: Longest Common Subsequence](#-sample-problem-2-longest-common-subsequence)
  - [1️⃣3️⃣ **Master Problem Set**](#1️⃣3️⃣-master-problem-set)
    - [🎯 Comprehensive Problem List by Pattern](#-comprehensive-problem-list-by-pattern)
    - [🎓 Study Path by Difficulty](#-study-path-by-difficulty)
  - [1️⃣4️⃣ **Memory Aids**](#1️⃣4️⃣-memory-aids)
    - [🧠 The DP Decision Framework](#-the-dp-decision-framework)
    - [📐 Essential Formulas \& Recurrences](#-essential-formulas--recurrences)
    - [🎪 Pattern Recognition Cheat Sheet](#-pattern-recognition-cheat-sheet)
    - [💡 Complexity Quick Reference](#-complexity-quick-reference)
    - [🎯 Interview Day Mnemonics](#-interview-day-mnemonics)
  - [🎓 Final Words](#-final-words)
    - [🎯 The Path to Mastery:](#-the-path-to-mastery)
    - [🚀 Success Strategies:](#-success-strategies)
    - [💪 You've Got This!](#-youve-got-this)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# 🔄 Dynamic Programming Pattern - Complete Interview Guide

## 1️⃣ **Pattern Overview**

### 🎯 Core Concept

**Input → Process → Output Flow:**

```
Input: Problem with overlapping subproblems + optimal substructure
   ↓
Process: Break into subproblems, store solutions, build up answer
   ↓
Output: Optimal solution using cached results
```

**Dynamic Programming (DP)** is an optimization technique that solves complex problems by breaking them down into simpler overlapping subproblems, solving each subproblem once, and storing the results to avoid redundant calculations. Think of it as "smart recursion with memory" 🧠💾!

### 🎪 When to Use This Pattern

✅ **Use Dynamic Programming when:**

- Problem has **overlapping subproblems** (same subproblems solved multiple times)
- Problem exhibits **optimal substructure** (optimal solution contains optimal solutions to subproblems)
- Need to find **optimal** value (min/max/count)
- Counting number of ways to do something
- Decision problems ("can we achieve X?")
- Can define recurrence relation

❌ **Don't use when:**

- No overlapping subproblems (use divide \& conquer instead)
- Greedy approach works optimally
- Need actual path/sequence (may need backtracking)
- Problem is NP-complete with no DP structure


### ⏱️ Complexity Overview

| Approach | Time Complexity | Space Complexity | Explanation |
| :-- | :-- | :-- | :-- |
| **Naive Recursion** | O(2^n) to O(n!) | O(n) stack | Exponential - solves same subproblems repeatedly |
| **Top-Down (Memoization)** | O(n × m) typical | O(n × m) | Store results in memo table |
| **Bottom-Up (Tabulation)** | O(n × m) typical | O(n × m) | Build solution iteratively |
| **Space Optimized** | O(n × m) | O(m) or O(1) | Use only necessary rows/columns |

**🎯 The DP Advantage:** Transforms exponential time to polynomial time!

***

## 2️⃣ **Pattern Recognition \& Detection**

### 🔍 Key Problem Signals

| Signal | Example Keywords | Pattern Indicator |
| :-- | :-- | :-- |
| 🎯 **Optimization** | "maximum", "minimum", "longest", "shortest" | Need optimal solution |
| 🔢 **Counting** | "how many ways", "number of", "count" | Count possibilities |
| ✅ **Decision** | "is it possible", "can we", "exists" | Boolean DP |
| 🔄 **Choices** | "choose or skip", "take or leave", "two options" | Decision tree |
| 📊 **Subproblems** | "prefix", "suffix", "subsequence", "substring" | Overlapping structure |
| 🎭 **State Dependency** | "previous", "depends on", "using results from" | Build on prior solutions |

### 🎨 Visual Pattern Recognition

```
Problem Type Identifier:
========================

📋 "Find the LONGEST increasing subsequence"
    ↓      ↓            ↓
    🎯  Optimization   Subproblem structure
    
Can we define: LIS[i] = longest subsequence ending at i?
Does it use: LIS[j] where j < i?

✅ DYNAMIC PROGRAMMING! ✅

Why? 
1. Optimization goal (longest) ✓
2. Overlapping subproblems ✓  
3. Optimal substructure ✓
4. Recurrence relation exists ✓
```


### 📊 The Two Pillars of DP

```
Pillar 1: OVERLAPPING SUBPROBLEMS 🔄
========================================

Example: Fibonacci(5)
                fib(5)
              /        \
          fib(4)        fib(3)  ← Computed again!
         /      \       /     \
     fib(3)   fib(2) fib(2) fib(1)
     /    \
  fib(2) fib(1)

Notice: fib(3) computed 2 times
        fib(2) computed 3 times
        
❌ Without DP: Exponential recalculation
✅ With DP: Calculate once, store, reuse


Pillar 2: OPTIMAL SUBSTRUCTURE 🏗️
========================================

Example: Shortest path from A to C
         Must use shortest path from A to B

    A ──2──→ B ──3──→ C
    └────────7────────→

Optimal A→C = Optimal(A→B) + Optimal(B→C)
            = 2 + 3 = 5 (not 7)

✅ Optimal solution built from optimal subsolutions
```


### 🎭 DP Recognition Flowchart

```
                    🤔 Problem Analysis Start
                              |
                    ┌─────────┴─────────┐
                    │ Can break into    │
                    │ subproblems?      │
                    └─────────┬─────────┘
                              |
                    ┌─────────┴─────────┐
                    | YES ✅           NO ❌
                    ↓                    ↓
          ┌─────────────────┐      Try different
          │ Subproblems     │      pattern (Greedy,
          │ overlap?        │      Two Pointers, etc.)
          └─────────┬───────┘
                    |
          ┌─────────┴─────────┐
          | YES ✅           NO ❌
          ↓                    ↓
    ┌──────────────┐     Divide & Conquer
    │ Has optimal  │     (Merge Sort, etc.)
    │ substructure?│
    └──────┬───────┘
           |
      ┌────┴────┐
      | YES ✅  NO ❌
      ↓          ↓
  ┌────────┐  Backtracking
  │   DP!  │  or Greedy
  │  🎯    │
  └────────┘
```


### 🎪 Common DP Patterns

```
Pattern Categories:
==================

1. LINEAR DP 📏
   - 1D array problems
   - States: dp[i]
   - Examples: Climbing Stairs, House Robber

2. 2D DP 📊
   - Grid/matrix problems
   - States: dp[i][j]
   - Examples: Unique Paths, Edit Distance

3. SEQUENCE DP 📝
   - Subsequence/substring problems
   - Compare elements
   - Examples: LIS, LCS

4. KNAPSACK DP 🎒
   - Include/exclude decisions
   - Weight/capacity constraints
   - Examples: 0/1 Knapsack, Subset Sum

5. INTERVAL DP 🔄
   - Process ranges/intervals
   - States: dp[i][j] = solution for range [i,j]
   - Examples: Burst Balloons, Matrix Chain

6. STATE MACHINE DP 🤖
   - Multiple states per position
   - State transitions
   - Examples: Stock Buy/Sell, Paint House

7. TREE DP 🌳
   - Recursion on tree structure
   - States at each node
   - Examples: Binary Tree Max Path, House Robber III
```


***

## 3️⃣ **Standard Algorithm Templates**

### 🎯 Template 1: Top-Down (Memoization)

```python
def dp_top_down(input_data):
    """
    🎯 Top-Down DP (Memoization) Template
    Recursive approach with caching
    """
    # 1️⃣ Initialize memoization structure
    memo = {}  # 📊 Dictionary or array to cache results
    
    def dp(state):
        """
        Recursive helper function
        state: represents current subproblem (could be int, tuple, etc.)
        """
        # 2️⃣ Base case - simplest subproblem
        if base_case_condition(state):
            return base_case_value
        
        # 3️⃣ Check if already computed
        if state in memo:
            return memo[state]  # 🔄 Return cached result
        
        # 4️⃣ Recurrence relation - break problem into subproblems
        result = combine(
            dp(next_state_1),
            dp(next_state_2),
            # ... other states
        )
        
        # 5️⃣ Store result in memo
        memo[state] = result
        
        return result
    
    # 6️⃣ Start recursion from original problem
    return dp(initial_state)


# 🎪 Example: Fibonacci with Memoization
def fib_memo(n):
    """Calculate nth Fibonacci number - Top Down"""
    memo = {}
    
    def dp(i):
        # Base cases
        if i <= 1:
            return i
        
        # Check memo
        if i in memo:
            return memo[i]
        
        # Recurrence: fib(n) = fib(n-1) + fib(n-2)
        memo[i] = dp(i - 1) + dp(i - 2)
        return memo[i]
    
    return dp(n)
```


### 📊 Template 2: Bottom-Up (Tabulation)

```python
def dp_bottom_up(input_data):
    """
    🎯 Bottom-Up DP (Tabulation) Template
    Iterative approach building from base cases
    """
    # 1️⃣ Initialize DP table
    n = len(input_data)
    dp = [initial_value] * (n + 1)  # 📊 Size depends on problem
    
    # 2️⃣ Set base cases
    dp[^0] = base_case_value_0
    dp[^1] = base_case_value_1  # if needed
    
    # 3️⃣ Fill table iteratively using recurrence relation
    for i in range(2, n + 1):  # 🔄 Build from smaller to larger
        # 4️⃣ Apply recurrence relation
        dp[i] = combine(dp[i-1], dp[i-2], input_data[i])
    
    # 5️⃣ Return final answer
    return dp[n]


# 🎪 Example: Fibonacci with Tabulation
def fib_tab(n):
    """Calculate nth Fibonacci number - Bottom Up"""
    if n <= 1:
        return n
    
    # Initialize table
    dp = [^0] * (n + 1)
    dp[^0], dp[^1] = 0, 1
    
    # Fill table
    for i in range(2, n + 1):
        dp[i] = dp[i-1] + dp[i-2]  # 🔄 Recurrence
    
    return dp[n]
```


### 🎯 Template 3: 2D DP

```python
def dp_2d(grid):
    """
    🎯 2D DP Template
    For grid/matrix problems
    """
    # 1️⃣ Get dimensions
    rows, cols = len(grid), len(grid[^0])
    
    # 2️⃣ Initialize DP table
    dp = [[^0] * cols for _ in range(rows)]
    
    # 3️⃣ Set base cases (first row/column)
    dp[^0][^0] = initial_value
    
    for i in range(1, rows):
        dp[i][^0] = base_case_row(dp, i)
    
    for j in range(1, cols):
        dp[^0][j] = base_case_col(dp, j)
    
    # 4️⃣ Fill table using recurrence
    for i in range(1, rows):
        for j in range(1, cols):
            # 🔄 Typically combines dp[i-1][j], dp[i][j-1], etc.
            dp[i][j] = recurrence(dp[i-1][j], dp[i][j-1], grid[i][j])
    
    # 5️⃣ Return answer (usually bottom-right)
    return dp[rows-1][cols-1]


# 🎪 Example: Unique Paths in Grid
def uniquePaths(m, n):
    """Count paths from top-left to bottom-right"""
    dp = [[^0] * n for _ in range(m)]
    
    # Base cases: first row and column all 1
    for i in range(m):
        dp[i][^0] = 1
    for j in range(n):
        dp[^0][j] = 1
    
    # Fill table
    for i in range(1, m):
        for j in range(1, n):
            # Can arrive from top or left
            dp[i][j] = dp[i-1][j] + dp[i][j-1]
    
    return dp[m-1][n-1]
```


### 💾 Template 4: Space-Optimized DP

```python
def dp_space_optimized(n):
    """
    🎯 Space-Optimized DP Template
    When only need previous row/state
    """
    # 1️⃣ Instead of full table, use rolling arrays
    prev = [initial_value] * size  # 📊 Previous row/state
    curr = [initial_value] * size  # 📊 Current row/state
    
    # 2️⃣ Set base case
    prev[^0] = base_case
    
    # 3️⃣ Iterate and update
    for i in range(1, n):
        for j in range(size):
            # 🔄 Use prev to compute curr
            curr[j] = recurrence(prev, curr, j)
        
        # 4️⃣ Swap arrays
        prev, curr = curr, prev
    
    return prev[answer_index]


# 🎪 Example: Fibonacci Space-Optimized
def fib_optimized(n):
    """Calculate Fibonacci with O(1) space"""
    if n <= 1:
        return n
    
    prev2, prev1 = 0, 1  # Only need last 2 values
    
    for i in range(2, n + 1):
        curr = prev1 + prev2
        prev2, prev1 = prev1, curr  # 🔄 Slide window
    
    return prev1
```


***

## 4️⃣ **Common Interview Problem Types**

### 🎯 Essential Problems Every Candidate Should Know

**1️⃣ Climbing Stairs (LC 70)** - Count ways to reach top with 1 or 2 steps - **Key insight**: Classic 1D DP, fib(n) = fib(n-1) + fib(n-2)

**2️⃣ House Robber (LC 198)** - Max money robbing non-adjacent houses - **Key insight**: dp[i] = max(rob i + dp[i-2], skip i = dp[i-1])

**3️⃣ Coin Change (LC 322)** - Min coins to make amount - **Key insight**: Unbounded knapsack, dp[amount] = min(dp[amount - coin] + 1)

**4️⃣ Longest Increasing Subsequence (LC 300)** - Find longest increasing subsequence length - **Key insight**: dp[i] = max(dp[j] + 1) where arr[j] < arr[i]

**5️⃣ Unique Paths (LC 62)** - Count paths in grid (right/down only) - **Key insight**: 2D DP, dp[i][j] = dp[i-1][j] + dp[i][j-1]

**6️⃣ Edit Distance (LC 72)** - Min operations to convert string A to B - **Key insight**: Classic 2D string DP with insert/delete/replace

***

## 5️⃣ **Advanced Techniques \& Variations**

## 🔬 Technique 1: Linear DP (1D Problems)

### 📋 When to Use

- Single sequence/array input
- State depends only on previous elements
- Decision at each position
- Examples: climbing stairs, house robber, decode ways


### 🎯 Core Implementation Pattern

```python
def linear_dp_template(arr):
    """
    📏 Linear DP Template (1D)
    
    State: dp[i] = optimal solution using first i elements
    Recurrence: dp[i] = f(dp[i-1], dp[i-2], ..., arr[i])
    
    Time: O(n) | Space: O(n) or O(1) optimized
    """
    n = len(arr)
    
    # 1️⃣ Initialize DP array
    dp = [^0] * (n + 1)
    
    # 2️⃣ Base cases
    dp[^0] = base_case_0
    dp[^1] = base_case_1
    
    # 3️⃣ Build solution iteratively
    for i in range(2, n + 1):
        # 🔄 Recurrence relation
        dp[i] = max(
            arr[i-1] + dp[i-2],  # Include current
            dp[i-1]               # Exclude current
        )
    
    return dp[n]
```


### 📊 Visual Walkthrough

```
Example: House Robber [2, 7, 9, 3, 1]
Goal: Max money robbing non-adjacent houses

State Definition:
dp[i] = max money robbing houses 0..i-1

Recurrence:
dp[i] = max(rob house i-1 + dp[i-2],  ← rob current
            skip house i-1 = dp[i-1])  ← don't rob


Step-by-step Building:
=======================

Houses:  [2, 7, 9, 3, 1]
Index:    0  1  2  3  4

dp[^0] = 0  (no houses)
dp[^1] = 2  (rob house 0)
dp[^2] = max(7 + dp[^0], dp[^1]) = max(7, 2) = 7
        rob 1  ✅
        
dp[^3] = max(9 + dp[^1], dp[^2]) = max(9+2, 7) = 11
        rob 2  ✅
        
dp[^4] = max(3 + dp[^2], dp[^3]) = max(3+7, 11) = 11
        skip 3 ✅
        
dp[^5] = max(1 + dp[^3], dp[^4]) = max(1+11, 11) = 12
        rob 4  ✅

DP Table:
┌────┬────┬────┬────┬────┬────┐
│ 0  │ 2  │ 7  │ 11 │ 11 │ 12 │
└────┴────┴────┴────┴────┴────┘
  ↑                          ↑
 base                     answer

Houses robbed: 0, 2, 4 → 2 + 9 + 1 = 12 ✅
```


### 💻 Complete Problem Solutions

#### **Problem 1: Climbing Stairs (LC 70)**

```python
def climbStairs(n):
    """
    🎯 Count ways to climb n stairs (1 or 2 steps at a time)
    
    Example: n = 3
    Output: 3 (ways: [1,1,1], [1,2], [2,1])
    
    Recurrence: dp[i] = dp[i-1] + dp[i-2]
    (reach step i from i-1 with 1 step, or from i-2 with 2 steps)
    
    Time: O(n) | Space: O(1)
    """
    if n <= 2:
        return n
    
    # Space optimized: only need last 2 values
    prev2, prev1 = 1, 2  # dp[^1]=1, dp[^2]=2
    
    for i in range(3, n + 1):
        curr = prev1 + prev2
        prev2, prev1 = prev1, curr
    
    return prev1

# 📊 Tabulation version
def climbStairs_tab(n):
    """Full table approach for clarity"""
    if n <= 2:
        return n
    
    dp = [^0] * (n + 1)
    dp[^1], dp[^2] = 1, 2
    
    for i in range(3, n + 1):
        dp[i] = dp[i-1] + dp[i-2]
    
    return dp[n]

# 📊 Example trace for n=5
# dp[^1] = 1 (one way: [^1])
# dp[^2] = 2 (two ways: [1,1], [^2])
# dp[^3] = 3 (ways: [1,1,1], [1,2], [2,1])
# dp[^4] = 5 (ways: [1,1,1,1], [1,1,2], [1,2,1], [2,1,1], [2,2])
# dp[^5] = 8
```


#### **Problem 2: House Robber (LC 198)**

```python
def rob(nums):
    """
    🎯 Max money robbing non-adjacent houses
    
    Example: nums = [2,7,9,3,1]
    Output: 12 (rob houses 0,2,4 → 2+9+1)
    
    Recurrence: dp[i] = max(nums[i] + dp[i-2], dp[i-1])
    
    Time: O(n) | Space: O(1)
    """
    if not nums:
        return 0
    if len(nums) == 1:
        return nums[^0]
    
    # Space optimized
    prev2, prev1 = 0, 0
    
    for num in nums:
        # Rob current + prev2, or skip current (use prev1)
        curr = max(num + prev2, prev1)
        prev2, prev1 = prev1, curr
    
    return prev1

# 📊 Memoization version
def rob_memo(nums):
    """Top-down approach"""
    memo = {}
    
    def dp(i):
        # Base cases
        if i < 0:
            return 0
        if i == 0:
            return nums[^0]
        
        # Check memo
        if i in memo:
            return memo[i]
        
        # Recurrence
        memo[i] = max(
            nums[i] + dp(i - 2),  # Rob current
            dp(i - 1)             # Skip current
        )
        return memo[i]
    
    return dp(len(nums) - 1)

# 📊 Detailed trace for [2,7,9,3,1]
# i=0: max(2+0, 0) = 2
# i=1: max(7+0, 2) = 7
# i=2: max(9+2, 7) = 11
# i=3: max(3+7, 11) = 11
# i=4: max(1+11, 11) = 12 ✅
```


#### **Problem 3: Decode Ways (LC 91)**

```python
def numDecodings(s):
    """
    🎯 Count ways to decode string (A=1, B=2, ..., Z=26)
    
    Example: s = "226"
    Output: 3 (ways: "2,2,6"→BZ, "22,6"→VF, "2,26"→BZ)
    
    Recurrence: 
    dp[i] = dp[i-1] (if s[i] valid single digit) +
            dp[i-2] (if s[i-1:i+1] valid two digits)
    
    Time: O(n) | Space: O(1)
    """
    if not s or s[^0] == '0':
        return 0
    
    n = len(s)
    prev2, prev1 = 1, 1  # dp[^0]=1, dp[^1]=1
    
    for i in range(1, n):
        curr = 0
        
        # 1️⃣ Single digit decode
        if s[i] != '0':
            curr += prev1
        
        # 2️⃣ Two digit decode
        two_digit = int(s[i-1:i+1])
        if 10 <= two_digit <= 26:
            curr += prev2
        
        prev2, prev1 = prev1, curr
    
    return prev1

# 📊 Visual trace for "226"
# Position: 0(2)  1(2)  2(6)
#
# i=1: s[^1]='2' (valid single) + s[0:2]='22' (valid two)
#      dp[^1] = dp[^0] + dp[-1] = 1 + 1 = 2
#      Ways: "2,2" and "22"
#
# i=2: s[^2]='6' (valid single) + s[1:3]='26' (valid two)
#      dp[^2] = dp[^1] + dp[^0] = 2 + 1 = 3
#      Ways: "2,2,6", "22,6", "2,26"

# 📊 Edge cases
print(numDecodings("06"))    # 0 (leading zero invalid)
print(numDecodings("27"))    # 1 (only "2,7")
print(numDecodings("12"))    # 2 ("1,2" or "12")
```


#### **Problem 4: Min Cost Climbing Stairs (LC 746)**

```python
def minCostClimbingStairs(cost):
    """
    🎯 Min cost to reach top (can start from 0 or 1)
    
    Example: cost = [10,15,20]
    Output: 15 (start at 1, pay 15, reach top)
    
    Recurrence: dp[i] = cost[i] + min(dp[i-1], dp[i-2])
    
    Time: O(n) | Space: O(1)
    """
    n = len(cost)
    
    # Space optimized
    prev2, prev1 = cost[^0], cost[^1]
    
    for i in range(2, n):
        curr = cost[i] + min(prev1, prev2)
        prev2, prev1 = prev1, curr
    
    # Can step from n-1 or n-2 to reach top
    return min(prev1, prev2)

# 📊 Full table version for clarity
def minCostClimbingStairs_tab(cost):
    n = len(cost)
    dp = [^0] * (n + 1)
    
    # Base cases: can start from step 0 or 1
    dp[^0] = cost[^0]
    dp[^1] = cost[^1]
    
    for i in range(2, n):
        # Pay current cost + min of previous two
        dp[i] = cost[i] + min(dp[i-1], dp[i-2])
    
    # Reach top from last or second-last step
    return min(dp[n-1], dp[n-2])

# 📊 Trace for cost = [10, 15, 20]
# dp[^0] = 10
# dp[^1] = 15
# dp[^2] = 20 + min(15, 10) = 30
# Answer: min(dp[^2], dp[^1]) = min(30, 15) = 15 ✅
#
# Optimal path: Start at index 1 → pay 15 → reach top
```


### 🎯 Linear DP Problem List

**1️⃣ Climbing Stairs (LC 70)** - Count ways to reach top - **Key insight**: Fibonacci pattern, dp[i] = dp[i-1] + dp[i-2]

**2️⃣ House Robber (LC 198)** - Max non-adjacent sum - **Key insight**: Choose rob current or skip

**3️⃣ Decode Ways (LC 91)** - Count string decodings - **Key insight**: Single digit + two digit possibilities

**4️⃣ Min Cost Climbing Stairs (LC 746)** - Min cost to reach top - **Key insight**: Cost + min of prev two steps

**5️⃣ Delete and Earn (LC 740)** - Max points deleting numbers - **Key insight**: Convert to house robber problem

***

## 🔬 Technique 2: Knapsack DP (0/1 \& Unbounded)

### 📋 When to Use

- Include/exclude decisions for items
- Capacity/weight constraint
- Maximize value or count combinations
- Examples: subset sum, coin change, partition


### 🎯 Core Implementation - 0/1 Knapsack

```python
def knapsack_01(weights, values, capacity):
    """
    🎒 0/1 Knapsack Template
    Each item used at most once
    
    State: dp[i][w] = max value using items 0..i with capacity w
    
    Recurrence:
    dp[i][w] = max(
        dp[i-1][w],                    # Don't take item i
        values[i] + dp[i-1][w-weight[i]]  # Take item i (if fits)
    )
    
    Time: O(n × capacity) | Space: O(capacity) optimized
    """
    n = len(weights)
    
    # 1️⃣ Initialize DP table
    dp = [[^0] * (capacity + 1) for _ in range(n + 1)]
    
    # 2️⃣ Fill table
    for i in range(1, n + 1):
        for w in range(capacity + 1):
            # Don't take item
            dp[i][w] = dp[i-1][w]
            
            # Take item if it fits
            if weights[i-1] <= w:
                dp[i][w] = max(
                    dp[i][w],
                    values[i-1] + dp[i-1][w - weights[i-1]]
                )
    
    return dp[n][capacity]


# 🎯 Space-Optimized Version
def knapsack_01_optimized(weights, values, capacity):
    """Use 1D array instead of 2D"""
    dp = [^0] * (capacity + 1)
    
    for i in range(len(weights)):
        # ⚠️ Iterate backwards to avoid using updated values
        for w in range(capacity, weights[i] - 1, -1):
            dp[w] = max(dp[w], values[i] + dp[w - weights[i]])
    
    return dp[capacity]
```


### 🎯 Core Implementation - Unbounded Knapsack

```python
def knapsack_unbounded(weights, values, capacity):
    """
    🎒 Unbounded Knapsack Template
    Each item can be used unlimited times
    
    Recurrence:
    dp[w] = max(dp[w], values[i] + dp[w - weights[i]])
    
    Time: O(n × capacity) | Space: O(capacity)
    """
    dp = [^0] * (capacity + 1)
    
    # For each capacity
    for w in range(capacity + 1):
        # Try each item
        for i in range(len(weights)):
            if weights[i] <= w:
                dp[w] = max(dp[w], values[i] + dp[w - weights[i]])
    
    return dp[capacity]
```


### 📊 Visual Walkthrough - 0/1 Knapsack

```
Example: weights = [1, 3, 4], values = [15, 20, 30], capacity = 4

Goal: Max value with weight ≤ 4

DP Table Construction:
======================

     Capacity →
     0   1   2   3   4
   ┌───┬───┬───┬───┬───┐
 0 │ 0 │ 0 │ 0 │ 0 │ 0 │  No items
   ├───┼───┼───┼───┼───┤
 1 │ 0 │15 │15 │15 │15 │  Item 0: w=1, v=15
   ├───┼───┼───┼───┼───┤
 2 │ 0 │15 │15 │20 │35 │  Item 1: w=3, v=20
   ├───┼───┼───┼───┼───┤
 3 │ 0 │15 │15 │20 │35 │  Item 2: w=4, v=30
   └───┴───┴───┴───┴───┘
                     ↑
                  answer

Key Decisions:
==============

At dp[^2][^4] (items 0,1 with capacity 4):
  Option 1: Don't take item 1 → dp[^1][^4] = 15
  Option 2: Take item 1 (w=3) → 20 + dp[^1][^1] = 20 + 15 = 35 ✅
  
At dp[^3][^4] (all items with capacity 4):
  Option 1: Don't take item 2 → dp[^2][^4] = 35 ✅
  Option 2: Take item 2 (w=4) → 30 + dp[^2][^0] = 30 + 0 = 30
  
Best: 35 (items 0 and 1)
```


### 💻 Complete Problem Solutions

#### **Problem 1: Partition Equal Subset Sum (LC 416)**

```python
def canPartition(nums):
    """
    🎯 Can partition array into two equal-sum subsets?
    
    Example: nums = [1,5,11,5]
    Output: True (partition: [1,5,5] and [^11])
    
    Insight: Find subset with sum = total_sum / 2 (0/1 knapsack)
    
    Time: O(n × sum) | Space: O(sum)
    """
    total = sum(nums)
    
    # If odd total, can't partition equally
    if total % 2 != 0:
        return False
    
    target = total // 2
    
    # DP: can we make sum = target?
    dp = [False] * (target + 1)
    dp[^0] = True  # Can always make sum 0
    
    # For each number
    for num in nums:
        # Iterate backwards (0/1 knapsack)
        for s in range(target, num - 1, -1):
            dp[s] = dp[s] or dp[s - num]
    
    return dp[target]

# 📊 Detailed trace for [1,5,11,5]
# total = 22, target = 11
#
# Initial: dp = [T, F, F, ..., F] (size 12)
#
# After num=1:  dp[^1] = True
#               dp = [T, T, F, F, F, F, F, F, F, F, F, F]
#
# After num=5:  dp[^5] = True, dp[^6] = True (1+5)
#               dp = [T, T, F, F, F, T, T, F, F, F, F, F]
#
# After num=11: dp[^11] = True, dp[^12] would be True (out of bounds)
#               dp = [T, T, F, F, F, T, T, F, F, F, F, T]
#
# After num=5:  dp[^10] = True (5+5), dp[^11] stays True
#               dp = [T, T, F, F, F, T, T, F, F, F, T, T]
#
# dp[^11] = True ✅ Can make sum 11!
```


#### **Problem 2: Coin Change (LC 322)**

```python
def coinChange(coins, amount):
    """
    🎯 Min coins needed to make amount (unbounded knapsack)
    
    Example: coins = [1,2,5], amount = 11
    Output: 3 (5+5+1)
    
    Recurrence: dp[i] = min(dp[i], 1 + dp[i - coin])
    
    Time: O(n × amount) | Space: O(amount)
    """
    # Initialize with infinity
    dp = [float('inf')] * (amount + 1)
    dp[^0] = 0  # Base case: 0 coins for amount 0
    
    # For each amount
    for i in range(1, amount + 1):
        # Try each coin
        for coin in coins:
            if coin <= i:
                dp[i] = min(dp[i], 1 + dp[i - coin])
    
    return dp[amount] if dp[amount] != float('inf') else -1

# 📊 Visual trace for coins=[1,2,5], amount=11
#
# Amount:  0   1   2   3   4   5   6   7   8   9  10  11
# dp:    [ 0, ∞,  ∞,  ∞,  ∞,  ∞,  ∞,  ∞,  ∞,  ∞,  ∞,  ∞]
#
# After processing:
# dp[^1] = min(∞, 1+dp[^0]) = 1           (use coin 1)
# dp[^2] = min(1+dp[^1], 1+dp[^0]) = 1     (use coin 2)
# dp[^3] = min(1+dp[^2], 1+dp[^1]) = 2     (use 2+1)
# dp[^4] = min(1+dp[^3], 1+dp[^2]) = 2     (use 2+2)
# dp[^5] = min(1+dp[^4], 1+dp[^3], 1+dp[^0]) = 1  (use coin 5) ✅
# dp[^6] = min(1+dp[^5], 1+dp[^4]) = 2     (5+1)
# dp[^10] = min(...) = 2                  (5+5)
# dp[^11] = min(1+dp[^10], 1+dp[^9], 1+dp[^6]) = 3 (5+5+1) ✅
#
# Final: [0, 1, 1, 2, 2, 1, 2, 2, 3, 3, 2, 3]
```


#### **Problem 3: Target Sum (LC 494)**

```python
def findTargetSumWays(nums, target):
    """
    🎯 Count ways to assign +/- to reach target sum
    
    Example: nums = [1,1,1,1,1], target = 3
    Output: 5 (ways to get sum=3 with +/-)
    
    Insight: Convert to subset sum problem
    P - N = target, P + N = total
    → P = (target + total) / 2
    
    Time: O(n × sum) | Space: O(sum)
    """
    total = sum(nums)
    
    # Check if possible
    if abs(target) > total or (target + total) % 2 != 0:
        return 0
    
    subset_sum = (target + total) // 2
    
    # Count subsets with given sum
    dp = [^0] * (subset_sum + 1)
    dp[^0] = 1  # One way to make 0: select nothing
    
    for num in nums:
        # Backwards iteration (0/1 knapsack)
        for s in range(subset_sum, num - 1, -1):
            dp[s] += dp[s - num]
    
    return dp[subset_sum]

# 📊 Trace for nums=[1,1,1,1,1], target=3
# total = 5, subset_sum = (3+5)/2 = 4
# Goal: count subsets summing to 4
#
# Initial: dp = [1, 0, 0, 0, 0]
#
# After 1st num=1:
#   dp = [1, 1, 0, 0, 0]  (can make 0 or 1)
#
# After 2nd num=1:
#   dp = [1, 2, 1, 0, 0]  (0: 1 way, 1: 2 ways, 2: 1 way)
#
# After 3rd num=1:
#   dp = [1, 3, 3, 1, 0]
#
# After 4th num=1:
#   dp = [1, 4, 6, 4, 1]
#
# After 5th num=1:
#   dp = [1, 5, 10, 10, 5]
#                      ↑
# dp[^4] = 5 ✅ (5 ways to select subset summing to 4)
```


#### **Problem 4: Ones and Zeroes (LC 474)**

```python
def findMaxForm(strs, m, n):
    """
    🎯 Max strings you can form with m zeros and n ones
    
    Example: strs = ["10","0001","111001","1","0"], m=5, n=3
    Output: 4 (use "10", "0001", "1", "0")
    
    Insight: 2D knapsack (capacity for 0s and 1s)
    
    Time: O(len(strs) × m × n) | Space: O(m × n)
    """
    # dp[i][j] = max strings with i zeros and j ones
    dp = [[^0] * (n + 1) for _ in range(m + 1)]
    
    for s in strs:
        # Count zeros and ones in current string
        zeros = s.count('0')
        ones = s.count('1')
        
        # Backwards iteration (0/1 knapsack)
        for i in range(m, zeros - 1, -1):
            for j in range(n, ones - 1, -1):
                # Take current string or skip
                dp[i][j] = max(
                    dp[i][j],                      # Skip
                    1 + dp[i - zeros][j - ones]    # Take
                )
    
    return dp[m][n]

# 📊 Example trace for strs=["10","0"], m=1, n=1
#
# String "10": zeros=1, ones=1
#   dp[^1][^1] = max(0, 1 + dp[^0][^0]) = 1
#
# String "0": zeros=1, ones=0
#   dp[^1][^0] = max(0, 1 + dp[^0][^0]) = 1
#   dp[^1][^1] stays 1 (can't fit both)
#
# Result: dp[^1][^1] = 1 (can only use one string)
```


### 🎯 Knapsack DP Problem List

**1️⃣ Partition Equal Subset Sum (LC 416)** - Split into equal sums - **Key insight**: 0/1 knapsack with target = sum/2

**2️⃣ Coin Change (LC 322)** - Min coins for amount - **Key insight**: Unbounded knapsack minimization

**3️⃣ Coin Change II (LC 518)** - Count ways to make amount - **Key insight**: Unbounded knapsack counting

**4️⃣ Target Sum (LC 494)** - Ways to assign +/- for target - **Key insight**: Convert to subset sum

**5️⃣ Ones and Zeroes (LC 474)** - Max strings with m 0s, n 1s - **Key insight**: 2D knapsack

***

## 🔬 Technique 3: Longest Common Subsequence (LCS) Pattern

### 📋 When to Use

- Comparing two sequences (strings/arrays)
- Finding common elements in order
- Edit distance problems
- Pattern matching between sequences


### 🎯 Core Implementation

```python
def lcs_template(text1, text2):
    """
    📝 Longest Common Subsequence Template
    
    State: dp[i][j] = LCS length of text1[0:i] and text2[0:j]
    
    Recurrence:
    if text1[i-1] == text2[j-1]:
        dp[i][j] = 1 + dp[i-1][j-1]  # Match! Extend LCS
    else:
        dp[i][j] = max(dp[i-1][j], dp[i][j-1])  # Skip from one
    
    Time: O(m × n) | Space: O(m × n)
    """
    m, n = len(text1), len(text2)
    
    # 1️⃣ Initialize DP table
    dp = [[^0] * (n + 1) for _ in range(m + 1)]
    
    # 2️⃣ Fill table
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if text1[i-1] == text2[j-1]:
                # ✅ Characters match
                dp[i][j] = 1 + dp[i-1][j-1]
            else:
                # ❌ Don't match, take max
                dp[i][j] = max(dp[i-1][j], dp[i][j-1])
    
    return dp[m][n]
```


### 📊 Visual Walkthrough

```
Example: text1 = "abcde", text2 = "ace"
Goal: Find longest common subsequence

DP Table Construction:
======================

       ""  a  c  e
    ┌───┬──┬──┬──┐
 "" │ 0 │0 │0 │0 │
    ├───┼──┼──┼──┤
 a  │ 0 │1 │1 │1 │  'a' matches text2[^0]
    ├───┼──┼──┼──┤
 b  │ 0 │1 │1 │1 │  No new matches
    ├───┼──┼──┼──┤
 c  │ 0 │1 │2 │2 │  'c' matches text2[^1]
    ├───┼──┼──┼──┤
 d  │ 0 │1 │2 │2 │  No new matches
    ├───┼──┼──┼──┤
 e  │ 0 │1 │2 │3 │  'e' matches text2[^2]
    └───┴──┴──┴──┘
                ↑
             answer = 3

LCS: "ace" ✅

Decision at each cell:
======================

dp[^1][^1]: text1[^0]='a', text2[^0]='a' → MATCH!
         dp[^1][^1] = 1 + dp[^0][^0] = 1

dp[^2][^1]: text1[^1]='b', text2[^0]='a' → NO MATCH
         dp[^2][^1] = max(dp[^1][^1], dp[^2][^0]) = max(1, 0) = 1

dp[^3][^2]: text1[^2]='c', text2[^1]='c' → MATCH!
         dp[^3][^2] = 1 + dp[^2][^1] = 2

dp[^5][^3]: text1[^4]='e', text2[^2]='e' → MATCH!
         dp[^5][^3] = 1 + dp[^4][^2] = 3
```


### 💻 Complete Problem Solutions

#### **Problem 1: Longest Common Subsequence (LC 1143)**

```python
def longestCommonSubsequence(text1, text2):
    """
    🎯 Find length of longest common subsequence
    
    Example: text1 = "abcde", text2 = "ace"
    Output: 3 (LCS = "ace")
    
    Time: O(m × n) | Space: O(m × n)
    """
    m, n = len(text1), len(text2)
    dp = [[^0] * (n + 1) for _ in range(m + 1)]
    
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if text1[i-1] == text2[j-1]:
                dp[i][j] = 1 + dp[i-1][j-1]
            else:
                dp[i][j] = max(dp[i-1][j], dp[i][j-1])
    
    return dp[m][n]

# 🎯 Space-Optimized Version (O(n) space)
def longestCommonSubsequence_optimized(text1, text2):
    """Only need previous row"""
    m, n = len(text1), len(text2)
    prev = [^0] * (n + 1)
    
    for i in range(1, m + 1):
        curr = [^0] * (n + 1)
        for j in range(1, n + 1):
            if text1[i-1] == text2[j-1]:
                curr[j] = 1 + prev[j-1]
            else:
                curr[j] = max(prev[j], curr[j-1])
        prev = curr
    
    return prev[n]

# 📊 Reconstruct actual LCS string
def getLCS(text1, text2):
    """Return the actual LCS string"""
    m, n = len(text1), len(text2)
    dp = [[^0] * (n + 1) for _ in range(m + 1)]
    
    # Build DP table
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if text1[i-1] == text2[j-1]:
                dp[i][j] = 1 + dp[i-1][j-1]
            else:
                dp[i][j] = max(dp[i-1][j], dp[i][j-1])
    
    # Backtrack to find LCS
    lcs = []
    i, j = m, n
    while i > 0 and j > 0:
        if text1[i-1] == text2[j-1]:
            lcs.append(text1[i-1])
            i -= 1
            j -= 1
        elif dp[i-1][j] > dp[i][j-1]:
            i -= 1
        else:
            j -= 1
    
    return ''.join(reversed(lcs))

# print(getLCS("abcde", "ace"))  # "ace"
```


#### **Problem 2: Edit Distance (LC 72)**

```python
def minDistance(word1, word2):
    """
    🎯 Min operations to convert word1 to word2
    Operations: insert, delete, replace
    
    Example: word1 = "horse", word2 = "ros"
    Output: 3 (horse → rorse → rose → ros)
    
    Recurrence:
    if word1[i-1] == word2[j-1]:
        dp[i][j] = dp[i-1][j-1]  # No operation needed
    else:
        dp[i][j] = 1 + min(
            dp[i-1][j],      # Delete from word1
            dp[i][j-1],      # Insert into word1
            dp[i-1][j-1]     # Replace
        )
    
    Time: O(m × n) | Space: O(m × n)
    """
    m, n = len(word1), len(word2)
    
    # Initialize DP table
    dp = [[^0] * (n + 1) for _ in range(m + 1)]
    
    # Base cases: empty string conversions
    for i in range(m + 1):
        dp[i][^0] = i  # Delete all from word1
    for j in range(n + 1):
        dp[^0][j] = j  # Insert all from word2
    
    # Fill table
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if word1[i-1] == word2[j-1]:
                # Characters match, no operation
                dp[i][j] = dp[i-1][j-1]
            else:
                # Take minimum of three operations
                dp[i][j] = 1 + min(
                    dp[i-1][j],      # Delete
                    dp[i][j-1],      # Insert
                    dp[i-1][j-1]     # Replace
                )
    
    return dp[m][n]

# 📊 Visual trace for "horse" → "ros"
#
#      ""  r  o  s
#   ┌───┬──┬──┬──┐
# ""│ 0 │1 │2 │3 │
#   ├───┼──┼──┼──┤
# h │ 1 │1 │2 │3 │
#   ├───┼──┼──┼──┤
# o │ 2 │2 │1 │2 │  'o' matches
#   ├───┼──┼──┼──┤
# r │ 3 │2 │2 │2 │  'r' matches
#   ├───┼──┼──┼──┤
# s │ 4 │3 │3 │2 │  's' matches
#   ├───┼──┼──┼──┤
# e │ 5 │4 │4 │3 │
#   └───┴──┴──┴──┘
#                ↑
#            answer = 3
#
# Operations: h→r (replace), delete o, delete e = 3 edits
```


#### **Problem 3: Delete Operation for Two Strings (LC 583)**

```python
def minDistance(word1, word2):
    """
    🎯 Min deletions to make two strings equal
    
    Example: word1 = "sea", word2 = "eat"
    Output: 2 (delete 's' from word1, delete 't' from word2)
    
    Insight: Length - LCS gives chars to delete from each
    
    Time: O(m × n) | Space: O(m × n)
    """
    m, n = len(word1), len(word2)
    
    # Find LCS length
    dp = [[^0] * (n + 1) for _ in range(m + 1)]
    
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if word1[i-1] == word2[j-1]:
                dp[i][j] = 1 + dp[i-1][j-1]
            else:
                dp[i][j] = max(dp[i-1][j], dp[i][j-1])
    
    lcs_length = dp[m][n]
    
    # Delete chars not in LCS from both strings
    return (m - lcs_length) + (n - lcs_length)

# 📊 Example: "sea" and "eat"
# LCS = "ea" (length 2)
# Deletions from "sea": 3 - 2 = 1 (delete 's')
# Deletions from "eat": 3 - 2 = 1 (delete 't')
# Total: 2 ✅
```


#### **Problem 4: Shortest Common Supersequence (LC 1092)**

```python
def shortestCommonSupersequence(str1, str2):
    """
    🎯 Find shortest string containing both as subsequences
    
    Example: str1 = "abac", str2 = "cab"
    Output: "cabac"
    
    Insight: Build LCS table, then reconstruct by merging
    
    Time: O(m × n) | Space: O(m × n)
    """
    m, n = len(str1), len(str2)
    
    # Build LCS table
    dp = [[^0] * (n + 1) for _ in range(m + 1)]
    
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if str1[i-1] == str2[j-1]:
                dp[i][j] = 1 + dp[i-1][j-1]
            else:
                dp[i][j] = max(dp[i-1][j], dp[i][j-1])
    
    # Reconstruct SCS by backtracking
    result = []
    i, j = m, n
    
    while i > 0 and j > 0:
        if str1[i-1] == str2[j-1]:
            # Part of LCS, include once
            result.append(str1[i-1])
            i -= 1
            j -= 1
        elif dp[i-1][j] > dp[i][j-1]:
            # Take from str1
            result.append(str1[i-1])
            i -= 1
        else:
            # Take from str2
            result.append(str2[j-1])
            j -= 1
    
    # Add remaining characters
    while i > 0:
        result.append(str1[i-1])
        i -= 1
    while j > 0:
        result.append(str2[j-1])
        j -= 1
    
    return ''.join(reversed(result))

# 📊 Example: "abac" and "cab"
# LCS: "ab" or "ca"
# SCS: merge both strings using LCS
# Result: "cabac" (contains "abac" and "cab")
```


### 🎯 LCS Pattern Problem List

**1️⃣ Longest Common Subsequence (LC 1143)** - LCS length - **Key insight**: Match chars or skip from one string

**2️⃣ Edit Distance (LC 72)** - Min operations word1→word2 - **Key insight**: Insert/delete/replace operations

**3️⃣ Delete Operation (LC 583)** - Min deletions to equalize - **Key insight**: Delete non-LCS chars

**4️⃣ Shortest Common Supersequence (LC 1092)** - Shortest containing both - **Key insight**: Merge using LCS

**5️⃣ Distinct Subsequences (LC 115)** - Count occurrences of pattern - **Key insight**: Count ways to match

***

## 🔬 Technique 4: Grid Path DP (2D)

### 📋 When to Use

- 2D grid/matrix navigation
- Counting paths with constraints
- Optimizing values across grid
- Movement restricted (usually right/down)


### 🎯 Core Implementation

```python
def grid_path_template(grid):
    """
    🗺️ Grid Path DP Template
    
    State: dp[i][j] = optimal value reaching cell (i,j)
    
    Recurrence:
    dp[i][j] = grid[i][j] + min/max(
        dp[i-1][j],   # From top
        dp[i][j-1]    # From left
    )
    
    Time: O(m × n) | Space: O(m × n) or O(n) optimized
    """
    if not grid:
        return 0
    
    m, n = len(grid), len(grid[^0])
    
    # 1️⃣ Initialize DP table
    dp = [[^0] * n for _ in range(m)]
    dp[^0][^0] = grid[^0][^0]
    
    # 2️⃣ Fill first row (can only come from left)
    for j in range(1, n):
        dp[^0][j] = dp[^0][j-1] + grid[^0][j]
    
    # 3️⃣ Fill first column (can only come from top)
    for i in range(1, m):
        dp[i][^0] = dp[i-1][^0] + grid[i][^0]
    
    # 4️⃣ Fill rest of table
    for i in range(1, m):
        for j in range(1, n):
            dp[i][j] = grid[i][j] + min(dp[i-1][j], dp[i][j-1])
    
    return dp[m-1][n-1]
```


### 📊 Visual Walkthrough

```
Example: Find minimum path sum in grid
Grid:
  1  3  1
  1  5  1
  4  2  1

Goal: Min sum from top-left to bottom-right (only right/down)

DP Table Construction:
======================

Step 1: Initialize
  1  ?  ?
  ?  ?  ?
  ?  ?  ?

Step 2: Fill first row
  1  4  5  ← Cumulative sum
  ?  ?  ?
  ?  ?  ?

Step 3: Fill first column
  1  4  5
  2  ?  ?  ← Cumulative sum
  6  ?  ?

Step 4: Fill remaining cells
  1  4  5
  2  7  6  ← min(2+5, 4+1) = 6
  6  8  7  ← min(6+2, 8+1) = 7
        ↑
     answer

Optimal Path:
  1 → 3 → 1
          ↓
          1
          ↓
      2 → 1
Total: 1+3+1+1+1 = 7 ✅

At each cell:
=============

dp[^1][^1] = grid[^1][^1] + min(dp[^0][^1], dp[^1][^0])
         = 5 + min(4, 2) = 7

dp[^1][^2] = grid[^1][^2] + min(dp[^0][^2], dp[^1][^1])
         = 1 + min(5, 7) = 6

dp[^2][^2] = grid[^2][^2] + min(dp[^1][^2], dp[^2][^1])
         = 1 + min(6, 8) = 7
```


### 💻 Complete Problem Solutions

#### **Problem 1: Unique Paths (LC 62)**

```python
def uniquePaths(m, n):
    """
    🎯 Count paths in m×n grid (only right/down moves)
    
    Example: m=3, n=2
    Output: 3 paths
    
    Recurrence: dp[i][j] = dp[i-1][j] + dp[i][j-1]
    
    Time: O(m × n) | Space: O(n) optimized
    """
    # Space-optimized: use 1D array
    dp = [^1] * n  # First row all 1s
    
    for i in range(1, m):
        for j in range(1, n):
            # Paths = from top + from left
            dp[j] += dp[j-1]
    
    return dp[n-1]

# 📊 Full 2D version for clarity
def uniquePaths_2d(m, n):
    dp = [[^1] * n for _ in range(m)]
    
    for i in range(1, m):
        for j in range(1, n):
            dp[i][j] = dp[i-1][j] + dp[i][j-1]
    
    return dp[m-1][n-1]

# 📊 Visual for m=3, n=3
#   1  1  1
#   1  2  3  ← 2 = 1+1, 3 = 2+1
#   1  3  6  ← 3 = 2+1, 6 = 3+3
#         ↑
#      answer = 6
```


#### **Problem 2: Minimum Path Sum (LC 64)**

```python
def minPathSum(grid):
    """
    🎯 Find path with minimum sum (top-left to bottom-right)
    
    Example: [[1,3,1],[1,5,1],[4,2,1]]
    Output: 7 (path: 1→3→1→1→1)
    
    Time: O(m × n) | Space: O(1) in-place
    """
    if not grid:
        return 0
    
    m, n = len(grid), len(grid[^0])
    
    # Modify grid in-place
    # Fill first row
    for j in range(1, n):
        grid[^0][j] += grid[^0][j-1]
    
    # Fill first column
    for i in range(1, m):
        grid[i][^0] += grid[i-1][^0]
    
    # Fill rest
    for i in range(1, m):
        for j in range(1, n):
            grid[i][j] += min(grid[i-1][j], grid[i][j-1])
    
    return grid[m-1][n-1]

# 📊 Space-preserved version
def minPathSum_preserved(grid):
    """Without modifying input"""
    m, n = len(grid), len(grid[^0])
    dp = [[^0] * n for _ in range(m)]
    dp[^0][^0] = grid[^0][^0]
    
    for j in range(1, n):
        dp[^0][j] = dp[^0][j-1] + grid[^0][j]
    
    for i in range(1, m):
        dp[i][^0] = dp[i-1][^0] + grid[i][^0]
    
    for i in range(1, m):
        for j in range(1, n):
            dp[i][j] = grid[i][j] + min(dp[i-1][j], dp[i][j-1])
    
    return dp[m-1][n-1]
```


#### **Problem 3: Unique Paths II (LC 63)**

```python
def uniquePathsWithObstacles(obstacleGrid):
    """
    🎯 Count paths with obstacles (1 = blocked, 0 = free)
    
    Example: [[0,0,0],[0,1,0],[0,0,0]]
    Output: 2 (obstacle at [1,1])
    
    Time: O(m × n) | Space: O(n)
    """
    if not obstacleGrid or obstacleGrid[^0][^0] == 1:
        return 0
    
    m, n = len(obstacleGrid), len(obstacleGrid[^0])
    dp = [^0] * n
    dp[^0] = 1
    
    for i in range(m):
        for j in range(n):
            if obstacleGrid[i][j] == 1:
                # Obstacle: no paths through here
                dp[j] = 0
            elif j > 0:
                # Paths from left + paths from top
                dp[j] += dp[j-1]
    
    return dp[n-1]

# 📊 Visual trace for [[0,0,0],[0,1,0],[0,0,0]]
#
# Initial: dp = [1, 0, 0]
#
# Row 0: [0,0,0]
#   j=0: dp[^0] = 1 (start)
#   j=1: dp[^1] = 0 + 1 = 1
#   j=2: dp[^2] = 0 + 1 = 1
#   dp = [1, 1, 1]
#
# Row 1: [0,1,0]
#   j=0: dp[^0] = 1 (from above)
#   j=1: obstacle! dp[^1] = 0
#   j=2: dp[^2] = 1 + 0 = 1
#   dp = [1, 0, 1]
#
# Row 2: [0,0,0]
#   j=0: dp[^0] = 1
#   j=1: dp[^1] = 1 + 0 = 1
#   j=2: dp[^2] = 1 + 1 = 2 ✅
#   dp = [1, 1, 2]
```


#### **Problem 4: Dungeon Game (LC 174)**

```python
def calculateMinimumHP(dungeon):
    """
    🎯 Min initial health to reach bottom-right (health must stay > 0)
    
    Example: [[-2,-3,3],[-5,-10,1],[10,30,-5]]
    Output: 7 (start with 7, end with 1)
    
    Insight: Work backwards from destination
    
    Time: O(m × n) | Space: O(n)
    """
    if not dungeon:
        return 0
    
    m, n = len(dungeon), len(dungeon[^0])
    
    # dp[i][j] = min health needed at (i,j) to survive
    dp = [[float('inf')] * n for _ in range(m)]
    
    # At destination, need at least 1 health after last cell
    dp[m-1][n-1] = max(1, 1 - dungeon[m-1][n-1])
    
    # Fill last row (can only go right)
    for j in range(n-2, -1, -1):
        dp[m-1][j] = max(1, dp[m-1][j+1] - dungeon[m-1][j])
    
    # Fill last column (can only go down)
    for i in range(m-2, -1, -1):
        dp[i][n-1] = max(1, dp[i+1][n-1] - dungeon[i][n-1])
    
    # Fill rest (backwards)
    for i in range(m-2, -1, -1):
        for j in range(n-2, -1, -1):
            # Min health needed from right or down
            min_needed = min(dp[i+1][j], dp[i][j+1])
            dp[i][j] = max(1, min_needed - dungeon[i][j])
    
    return dp[^0][^0]

# 📊 Trace backwards for [[-2,-3,3],[-5,-10,1],[10,30,-5]]
#
# Bottom-right [^2][^2]: -5
#   Need 1 health after: max(1, 1-(-5)) = 6
#
# [^2][^1]: 30
#   Need to survive [^2][^2]: max(1, 6-30) = 1
#
# [^1][^2]: 1
#   Need to survive [^2][^2]: max(1, 6-1) = 5
#
# Working backwards to [^0][^0]:
#   Final answer: 7 (start with 7 health)
```


### 🎯 Grid Path DP Problem List

**1️⃣ Unique Paths (LC 62)** - Count paths in grid - **Key insight**: Sum paths from top and left

**2️⃣ Minimum Path Sum (LC 64)** - Min sum path - **Key insight**: Min of top and left paths

**3️⃣ Unique Paths II (LC 63)** - Paths with obstacles - **Key insight**: Set obstacle cells to 0

**4️⃣ Dungeon Game (LC 174)** - Min health needed - **Key insight**: Work backwards from destination

**5️⃣ Cherry Pickup (LC 741)** - Max cherries two passes - **Key insight**: Two simultaneous paths DP

***

## 6️⃣ **Comprehensive Comparison Table**

| 🎯 **Approach** | ⏰ **Time Complexity** | 💾 **Space Complexity** | 🛠️ **Best Use Cases** | 📝 **Key Insights** | 🎪 **Template Pattern** |
| :-- | :-- | :-- | :-- | :-- | :-- |
| **Linear 1D DP** | O(n) | O(n) or O(1) | Single sequence, decisions at each position | State depends on previous elements | Initialize base → Fill array → Return dp[n] |
| **Knapsack 0/1** | O(n × capacity) | O(capacity) | Include/exclude items, capacity constraint | Iterate backwards for 1D optimization | For each item → For capacity (reverse) → Update |
| **Unbounded Knapsack** | O(n × capacity) | O(capacity) | Unlimited items, coin change variants | Iterate forwards (can reuse) | For each capacity → Try all items → Update |
| **LCS Pattern** | O(m × n) | O(m × n) or O(n) | Compare two sequences, edit distance | Match chars or skip from one sequence | Build table → if match: diagonal+1 → else: max(top,left) |
| **Grid Path 2D** | O(m × n) | O(m × n) or O(n) | 2D navigation, path counting/optimization | Combine results from possible sources | Fill edges → Fill interior from top/left → Return corner |
| **State Machine** | O(n × states) | O(n × states) or O(states) | Multiple states per position, transitions | Track state at each step | For position → For each state → Transition logic |
| **Interval DP** | O(n³) | O(n²) | Process ranges/subarrays | dp[i][j] = optimal for range [i,j] | For length → For start → For split point → Combine |


***

## 7️⃣ **Problem-to-Approach Mapping**

| **Problem Type** | **🥇 Primary** | **🥈 Secondary** | **🥉 Alternative** | **Example Problems** |
| :-- | :-- | :-- | :-- | :-- |
| **Single sequence decisions** | Linear 1D DP | State Machine | - | Climbing Stairs (LC 70), House Robber (LC 198) |
| **Two sequence comparison** | LCS Pattern | 2D DP | - | Edit Distance (LC 72), LCS (LC 1143) |
| **Subset with target sum** | 0/1 Knapsack | Backtracking | - | Partition Equal Subset (LC 416), Target Sum (LC 494) |
| **Unlimited items** | Unbounded Knapsack | - | - | Coin Change (LC 322), Coin Change II (LC 518) |
| **Grid navigation** | Grid Path 2D | DFS + Memo | - | Unique Paths (LC 62), Min Path Sum (LC 64) |
| **Buy/sell with states** | State Machine | Linear DP | - | Stock Buy/Sell (LC 121-123, 309, 714) |
| **Palindrome problems** | Interval DP | 2D DP | - | Longest Palindromic Substring (LC 5), Palindrome Partitioning (LC 132) |
| **String partitioning** | Interval DP | Linear DP + Hash | - | Word Break (LC 139), Palindrome Partitioning II (LC 132) |
| **Tree problems** | Tree DP (DFS) | - | - | House Robber III (LC 337), Binary Tree Max Path (LC 124) |
| **Count ways** | Linear DP or Knapsack | Combinatorics | - | Decode Ways (LC 91), Unique Paths (LC 62) |


***

## 8️⃣ **Performance Characteristics**

| **Input Size** | **O(n)** | **O(n²)** | **O(n × m)** | **O(n³)** |
| :-- | :-- | :-- | :-- | :-- |
| **n ≤ 100** | ✅ Instant | ✅ Instant | ✅ Instant | ✅ <10ms |
| **n ≤ 1,000** | ✅ <1ms | ✅ <50ms | ✅ <100ms | ⚠️ ~1s |
| **n ≤ 10,000** | ✅ <10ms | ⚠️ ~1s | ⚠️ Variable | ❌ Timeout |
| **n ≤ 100,000** | ✅ <100ms | ❌ Timeout | ⚠️ If m small | ❌ Impossible |
| **n ≤ 1,000,000** | ✅ ~1s | ❌ Impossible | ❌ Usually timeout | ❌ Impossible |

**🎯 Space Optimization Impact:**

- ✅ O(n) → O(1): Significant for large n (reduces memory by factor of n)
- ✅ O(n²) → O(n): Critical for n > 1000 (1M cells → 1K cells)
- ⚠️ May require backwards iteration or careful update order

***

## 9️⃣ **Selection Decision Tree**

```
                    📋 Dynamic Programming Problem
                              |
                    ┌─────────┴─────────┐
                    │ How many input    │
                    │ sequences?        │
                    └─────────┬─────────┘
                              |
            ┌─────────────────┼─────────────────┐
            |                 |                 |
         ONE 1️⃣           TWO 2️⃣           GRID 🗺️
            |                 |                 |
    ┌───────┴───────┐    ┌────┴────┐    ┌──────┴──────┐
    │ LINEAR or     │    │ LCS or  │    │ 2D GRID     │
    │ KNAPSACK?     │    │ 2D DP?  │    │ PATH DP     │
    └───────┬───────┘    └────┬────┘    └──────┬──────┘
            |                 |                 |
    ┌───────┴────────┐        |          ┌─────┴──────┐
    |                |        |          | Count or   |
Has capacity    Sequential    |          | Optimize?  |
constraint?     decisions?    |          └─────┬──────┘
    |                |        |                |
  YES ✅           NO ❌      |          ┌─────┴──────┐
    |                |        |          |            |
 ┌──┴───┐      ┌────┴────┐   |        COUNT      OPTIMIZE
 |      |      | LINEAR  |   |          |            |
0/1  UNBND     | 1D DP   |   |       Unique      Min Path
 |      |      |         |   |       Paths       Sum, etc.
LC416 LC322  LC70, 198   |   |
              |          |   |
              |    Comparing  |
              |    strings?   |
              |          |    |
              |        YES ✅  |
              |          |    |
              |      ┌───┴────┐
              |      | LCS    |
              |      | PATTERN|
              |      └───┬────┘
              |          |
              |    LC1143, 72
              |
      ┌───────┴────────┐
      | Process ranges?|
      └───────┬────────┘
              |
            YES ✅
              |
        ┌─────┴──────┐
        | INTERVAL   |
        | DP         |
        └─────┬──────┘
              |
         LC5, 516
```

**🎯 Quick Decision Checklist:**

1️⃣ **Is there capacity/weight constraint?**

- YES → Knapsack (0/1 or Unbounded)
- NO → Continue

2️⃣ **How many input sequences?**

- 1 sequence → Linear 1D or Knapsack
- 2 sequences → LCS pattern
- Grid → 2D Grid DP

3️⃣ **What's the goal?**

- Count ways → Usually linear or grid counting
- Optimize value → Check constraint type
- Boolean decision → Knapsack or linear

4️⃣ **Processing order?**

- Sequential left-to-right → Linear DP
- Ranges/intervals → Interval DP
- States with transitions → State Machine DP

***

## 🔟 **Common Pitfalls Analysis**

### 🚨 Critical Bug Example: Wrong Base Case in Fibonacci

#### ❌ WRONG CODE (with bugs):

```python
def fib_WRONG(n):
    """
    🐛 BUG-RIDDEN Fibonacci Implementation
    Multiple critical errors!
    """
    # Bug 1: Wrong size - off by one!
    dp = [^0] * n  # ❌ Should be n+1
    
    # Bug 2: Missing base case check
    dp[^0] = 0
    dp[^1] = 1  # ❌ Crashes when n=0!
    
    # Bug 3: Wrong range
    for i in range(2, n):  # ❌ Should be n+1
        dp[i] = dp[i-1] + dp[i-2]
    
    # Bug 4: Wrong return index
    return dp[n-1]  # ❌ Should be dp[n]

# 🔍 Let's trace bugs with n=5
```


### 📊 Execution Trace - WRONG vs EXPECTED:

| Input n | WRONG Code Behavior | Expected | Issue |
| :-- | :-- | :-- | :-- |
| **n=0** | `IndexError: list index out of range` | 0 | ❌ dp[^1] doesn't exist when dp size is 0 |
| Expected | Should return 0 immediately | - | Missing edge case handling |
| **n=1** | `dp = [^0]`, tries `dp[^1] = 1` | 1 | ❌ IndexError, array too small |
| Expected | Should return 1 | - | Array size should be n+1 |
| **n=5** | `dp = [0,0,0,0,0]` (size 5) | - | ❌ Missing slot for dp[^2] |
| After init | `dp = [0,1,0,0,0]` | `[0,1,0,0,0,0]` | Bug \#1: wrong size |
| Loop | `range(2, 5)` → i=2,3,4 | `range(2, 6)` | Bug \#3: doesn't compute dp[^2] |
| After loop | `dp = [0,1,1,2,3]` | `[0,1,1,2,3,5]` | Missing dp[^2] calculation |
| Return | `dp[^4] = 3` | `dp[^5] = 5` | ❌ Bug \#4: returns 4th Fibonacci (index 4) instead of 5th |
| **Correct Answer** | Should be 5 | 5 | Returns 3 instead! |

### 🔬 Detailed Bug Breakdown:

**🐛 Bug \#1: Array Size Off-By-One**

```python
# ❌ WRONG: Array too small
dp = [^0] * n  # For n=5: creates [0,0,0,0,0] - only indices 0-4

# ✅ CORRECT: Need space for dp[n]
dp = [^0] * (n + 1)  # For n=5: creates [0,0,0,0,0,0] - indices 0-5
```

**Impact:** Can't store dp[n], IndexError or wrong answer

**🐛 Bug \#2: No Edge Case Validation**

```python
# ❌ WRONG: Crashes immediately
dp[^0] = 0
dp[^1] = 1  # Crashes when n=0 (dp has size 0)

# ✅ CORRECT: Handle edge cases first
if n <= 1:
    return n
dp = [^0] * (n + 1)
dp[^0], dp[^1] = 0, 1
```

**Impact:** Runtime error for small inputs

**🐛 Bug \#3: Wrong Loop Range**

```python
# ❌ WRONG: Doesn't compute final answer
for i in range(2, n):  # For n=5: i=2,3,4 (stops before 5!)
    dp[i] = dp[i-1] + dp[i-2]

# ✅ CORRECT: Include n
for i in range(2, n + 1):  # For n=5: i=2,3,4,5
    dp[i] = dp[i-1] + dp[i-2]
```

**Impact:** dp[n] never computed, still has initial value

**🐛 Bug \#4: Wrong Return Index**

```python
# ❌ WRONG: Returns (n-1)th Fibonacci number
return dp[n-1]  # For n=5: returns dp[^4]=3 instead of dp[^5]=5

# ✅ CORRECT: Return nth Fibonacci
return dp[n]  # For n=5: returns dp[^5]=5
```

**Impact:** Always returns previous Fibonacci number

### ✅ CORRECT CODE Comparison:

```python
def fib_CORRECT(n):
    """
    ✅ CORRECT Fibonacci Implementation
    All bugs fixed!
    """
    # ✅ Fix Bug 2: Handle edge cases
    if n <= 1:
        return n
    
    # ✅ Fix Bug 1: Correct array size
    dp = [^0] * (n + 1)
    dp[^0], dp[^1] = 0, 1
    
    # ✅ Fix Bug 3: Include n in range
    for i in range(2, n + 1):
        dp[i] = dp[i-1] + dp[i-2]
    
    # ✅ Fix Bug 4: Return correct index
    return dp[n]

# 📊 Trace with n=5
# Edge case: n=5 > 1, continue
# Initialize: dp = [0, 1, 0, 0, 0, 0]
# i=2: dp[^2] = dp[^1] + dp[^0] = 1 + 0 = 1
# i=3: dp[^3] = dp[^2] + dp[^1] = 1 + 1 = 2
# i=4: dp[^4] = dp[^3] + dp[^2] = 2 + 1 = 3
# i=5: dp[^5] = dp[^4] + dp[^3] = 3 + 2 = 5 ✅
# Final: dp = [0, 1, 1, 2, 3, 5]
# Return: dp[^5] = 5 ✅ CORRECT!
```


### 🚨 Another Common Bug: 2D DP Index Confusion

#### ❌ WRONG CODE:

```python
def uniquePaths_WRONG(m, n):
    """🐛 Common 2D DP mistakes"""
    # Bug 1: Swapped dimensions
    dp = [[^0] * m for _ in range(n)]  # ❌ Should be m rows, n cols
    
    # Bug 2: Wrong base case range
    for i in range(m):  # ❌ Out of bounds!
        dp[i][^0] = 1
    
    return dp[m-1][n-1]  # ❌ Index error!

# ✅ CORRECT:
def uniquePaths_CORRECT(m, n):
    """✅ Proper dimension handling"""
    dp = [[^0] * n for _ in range(m)]  # m rows, n columns
    
    # Base cases
    for i in range(m):
        dp[i][^0] = 1
    for j in range(n):
        dp[^0][j] = 1
    
    for i in range(1, m):
        for j in range(1, n):
            dp[i][j] = dp[i-1][j] + dp[i][j-1]
    
    return dp[m-1][n-1]
```


### 🎯 Key Takeaways from Bug Analysis:

| Bug Category | Impact | Prevention |
| :-- | :-- | :-- |
| **Off-by-one array size** | IndexError or wrong answer | Always use `n+1` for dp array |
| **Missing edge cases** | Runtime crashes | Check `n <= 1` before array operations |
| **Wrong loop range** | Incomplete computation | Use `range(start, n+1)` to include n |
| **Wrong return index** | Off-by-one in answer | Return `dp[n]`, not `dp[n-1]` |
| **2D dimension confusion** | Index errors | Double-check: m rows, n columns |


***

## 1️⃣1️⃣ **Interview Success Tips**

### 🎯 Problem Recognition Signals

**🚨 Immediate DP Indicators:**


| Signal Phrase | Confidence | Example Problems |
| :-- | :-- | :-- |
| **"optimal"** + **"subproblem"** | 🔥 99% | Edit Distance, LIS |
| **"count ways"** or **"number of"** | 🔥 95% | Climbing Stairs, Decode Ways |
| **"maximum/minimum"** + **choices** | 🔥 90% | House Robber, Coin Change |
| **"subsequence"** or **"substring"** | 🔥 85% | LCS, Palindrome problems |
| **"partition"** or **"subset"** | 🔥 85% | Partition Equal Subset |
| **Multiple passes** through data | 🔥 80% | Stock problems, Cherry Pickup |
| **"can we"** or **"is it possible"** | 🔥 75% | Word Break, Target Sum |

### 🎪 Optimization Strategy Table

| Goal | Strategy | Example | Impact |
| :-- | :-- | :-- | :-- |
| **Reduce space O(n²)→O(n)** | Use rolling array/2 rows | LCS, Grid Path | Critical for large n |
| **Reduce space O(n)→O(1)** | Track only needed variables | Fibonacci, House Robber | Minimal memory |
| **Avoid recomputation** | Memoization over recursion | All DP problems | Exponential → Polynomial |
| **Early termination** | Return on first valid solution | Boolean DP | Saves unnecessary computation |
| **State compression** | Bit masking for subsets | Traveling Salesman | Exponential states → Manageable |
| **Optimal substructure** | Build large from small solutions | All DP | Foundation of DP |

### 🚨 Common Edge Cases with Code Examples

#### **1️⃣ Empty or Single Element Input**

```python
def dp_with_edge_cases(arr):
    # Edge case 1: Empty input
    if not arr:
        return 0  # or appropriate default
    
    # Edge case 2: Single element
    if len(arr) == 1:
        return arr[^0]  # or problem-specific value
    
    # Normal DP logic...
    dp = [^0] * len(arr)
    dp[^0] = arr[^0]
    dp[^1] = max(arr[^0], arr[^1])  # Safe now!
    
    for i in range(2, len(arr)):
        dp[i] = max(dp[i-1], dp[i-2] + arr[i])
    
    return dp[-1]
```


#### **2️⃣ Negative Numbers**

```python
def maxSubArray(nums):
    """
    Handle arrays with negative numbers
    Kadane's algorithm (DP variant)
    """
    # Must initialize with first element, not 0!
    max_ending_here = nums[^0]
    max_so_far = nums[^0]
    
    for i in range(1, len(nums)):
        # Include current or start fresh
        max_ending_here = max(nums[i], max_ending_here + nums[i])
        max_so_far = max(max_so_far, max_ending_here)
    
    return max_so_far

# Example: [-2,-1] should return -1, not 0!
```


#### **3️⃣ Integer Overflow (Less Common in Python)**

```python
def coinChange(coins, amount):
    """
    Use float('inf') carefully
    """
    dp = [float('inf')] * (amount + 1)
    dp[^0] = 0
    
    for i in range(1, amount + 1):
        for coin in coins:
            if coin <= i and dp[i - coin] != float('inf'):
                # Check infinity before adding
                dp[i] = min(dp[i], dp[i - coin] + 1)
    
    # Return -1 if impossible, not infinity
    return dp[amount] if dp[amount] != float('inf') else -1
```


#### **4️⃣ 2D Grid Out of Bounds**

```python
def uniquePathsWithObstacles(grid):
    """
    Handle obstacles and boundaries properly
    """
    if not grid or grid[^0][^0] == 1:
        return 0  # Blocked start
    
    m, n = len(grid), len(grid[^0])
    dp = [[^0] * n for _ in range(m)]
    
    # Base case: start position
    dp[^0][^0] = 1
    
    # Fill first row (stop if obstacle)
    for j in range(1, n):
        dp[^0][j] = dp[^0][j-1] if grid[^0][j] == 0 else 0
    
    # Fill first column (stop if obstacle)
    for i in range(1, m):
        dp[i][^0] = dp[i-1][^0] if grid[i][^0] == 0 else 0
    
    # Fill rest
    for i in range(1, m):
        for j in range(1, n):
            if grid[i][j] == 1:
                dp[i][j] = 0  # Obstacle
            else:
                dp[i][j] = dp[i-1][j] + dp[i][j-1]
    
    return dp[m-1][n-1]
```


#### **5️⃣ String Index Misalignment**

```python
def longestCommonSubsequence(text1, text2):
    """
    Common mistake: off-by-one in string indexing
    """
    m, n = len(text1), len(text2)
    dp = [[^0] * (n + 1) for _ in range(m + 1)]
    
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            # ⚠️ CRITICAL: Use i-1 and j-1 for string indices!
            if text1[i-1] == text2[j-1]:  # NOT text1[i]!
                dp[i][j] = 1 + dp[i-1][j-1]
            else:
                dp[i][j] = max(dp[i-1][j], dp[i][j-1])
    
    return dp[m][n]
```


### ✅ Interview Debug Checklist

Before submitting, verify:

- [ ] ✅ **Edge case: n=0** - Returns appropriate value? No IndexError?
- [ ] ✅ **Edge case: n=1** - Base case handled correctly?
- [ ] ✅ **Array size: n+1?** - Have space for dp[n]?
- [ ] ✅ **Loop range: n+1?** - Computes dp[n]?
- [ ] ✅ **Base cases set?** - dp, dp initialized before loop?[^1]
- [ ] ✅ **2D indices correct?** - Using i-1, j-1 for strings/arrays?
- [ ] ✅ **Iteration direction?** - Backwards for 0/1 knapsack? Forwards for unbounded?
- [ ] ✅ **Return value check?** - Returning dp[n], not dp[n-1]?
- [ ] ✅ **Infinity handling?** - Converting to -1 or 0 when needed?
- [ ] ✅ **State transitions?** - Recurrence relation implemented correctly?
- [ ] ✅ **Space optimization?** - Using O(n) instead of O(n²) where possible?
- [ ] ✅ **Negative numbers?** - Initialize with first element, not 0?


### 💡 Interview Communication Framework

**🎤 The 5-Step DP Explanation:**

```
1️⃣ "This is a DP problem because..." (identify overlapping subproblems)
   Example: "We'd calculate fib(3) multiple times in naive recursion"

2️⃣ "I'll define my state as..." (what does dp[i] or dp[i][j] represent)
   Example: "dp[i] = maximum money robbing houses 0 through i"

3️⃣ "The base case is..." (smallest subproblem)
   Example: "dp[^0] = nums[^0], dp[^1] = max(nums[^0], nums[^1])"

4️⃣ "The recurrence relation is..." (how to build larger from smaller)
   Example: "dp[i] = max(rob i + dp[i-2], skip i = dp[i-1])"

5️⃣ "Time complexity is O(n) because... Space is O(n) but can optimize to O(1)"
```

**🎯 Sample Dialog:**

```
Interviewer: "Find minimum coins to make amount."

You: "This is a dynamic programming problem because:

1️⃣ We have overlapping subproblems - to make amount 11, 
   we might need to solve amount 10, 9, and 6 multiple times 
   depending on coin denominations.

2️⃣ I'll define dp[i] as the minimum coins needed to make amount i.

3️⃣ Base case: dp[^0] = 0 (zero coins for amount zero).

4️⃣ Recurrence: For each amount i, try each coin. If coin ≤ i,
   dp[i] = min(dp[i], 1 + dp[i-coin]).
   
   This is unbounded knapsack since we can reuse coins.

5️⃣ Time: O(amount × coins), Space: O(amount).
   
Let me code this up..."

[Proceeds to write clean, commented code]
```


### 🎯 Pattern-Specific Red Flags

**⚠️ When doing LCS/2D DP:**

- Using `text1[i]` instead of `text1[i-1]` → Off-by-one error
- Forgetting to initialize first row/column
- Mixing up m and n dimensions

**⚠️ When doing Knapsack:**

- Iterating forwards in 0/1 knapsack → Items used multiple times
- Iterating backwards in unbounded → Can't reuse items
- Not checking if item fits before accessing dp[i-weight]

**⚠️ When doing Linear DP:**

- Returning dp[n-1] when array size is n → Missing final answer
- Not handling n=0, n=1 edge cases → IndexError

***

## 1️⃣2️⃣ **ASCII Problem Solving Flow**

### 🎯 Sample Problem: House Robber

**Problem:** `nums = [^2][^7][^9][^3][^1]` - Max money robbing non-adjacent houses

```
📋 Input Visualization:
=======================
Houses:  [💰2, 💰7, 💰9, 💰3, 💰1]
Index:    0    1    2    3    4

Constraint: Cannot rob adjacent houses 🚫
Goal: Maximize money stolen 💵


🔧 Step 0: Define DP State
===========================
dp[i] = max money robbing houses 0..i

Recurrence:
dp[i] = max(
    nums[i] + dp[i-2],  ← Rob house i (skip i-1)
    dp[i-1]             ← Skip house i
)


🔧 Step 1: Initialize Base Cases
=================================
dp[^0] = nums[^0] = 2
dp[^1] = max(nums[^0], nums[^1]) = max(2, 7) = 7

DP Array: [2, 7, ?, ?, ?]


🔄 Step 2: Process House 2 (💰9)
=================================
Option A: Rob house 2 → 9 + dp[^0] = 9 + 2 = 11 💰
Option B: Skip house 2 → dp[^1] = 7

Houses:  [💰2, 💰7, 💰9, 💰3, 💰1]
          ✅   ❌   ✅   
          Rob       Rob

dp[^2] = max(11, 7) = 11 ✅

DP Array: [2, 7, 11, ?, ?]


🔄 Step 3: Process House 3 (💰3)
=================================
Option A: Rob house 3 → 3 + dp[^1] = 3 + 7 = 10
Option B: Skip house 3 → dp[^2] = 11 ✅

Houses:  [💰2, 💰7, 💰9, 💰3, 💰1]
          ✅   ❌   ✅   ❌
          Rob       Rob   Skip (better to keep 9)

dp[^3] = max(10, 11) = 11

DP Array: [2, 7, 11, 11, ?]


🔄 Step 4: Process House 4 (💰1)
=================================
Option A: Rob house 4 → 1 + dp[^2] = 1 + 11 = 12 💰✅
Option B: Skip house 4 → dp[^3] = 11

Houses:  [💰2, 💰7, 💰9, 💰3, 💰1]
          ✅   ❌   ✅   ❌   ✅
          Rob       Rob       Rob

dp[^4] = max(12, 11) = 12 ✅

DP Array: [2, 7, 11, 11, 12]
                          ↑
                       ANSWER


🏆 Final Result
===============
Maximum money: 12 💵
Houses robbed: [0, 2, 4] → 2 + 9 + 1 = 12 ✅


📊 Visual Summary
=================
Initial:  [💰2, 💰7, 💰9, 💰3, 💰1]
Solution: [✅ , ❌ , ✅ , ❌ , ✅ ]
          Rob     Skip  Rob  Skip  Rob
          
Path: 2 → (skip 7) → 9 → (skip 3) → 1 = 12


📊 DP Table Evolution
=====================
Step    DP Array          Decision
────────────────────────────────────
Init    [2, 7, ?, ?, ?]   Base cases
i=2     [2, 7, 11, ?, ?]  Rob 2 (11 > 7)
i=3     [2, 7, 11, 11, ?] Skip 3 (11 ≥ 10)
i=4     [2, 7, 11, 11, 12] Rob 4 (12 > 11) ✅


⏰ Complexity Analysis
======================
Time: O(n) - Single pass through array
Space: O(n) - DP array
Can optimize to O(1) with two variables!
```


### 🎭 Sample Problem 2: Longest Common Subsequence

**Problem:** `text1 = "abcde"`, `text2 = "ace"` - Find LCS length

```
📋 Input Visualization:
=======================
text1: a b c d e
text2: a c e

Goal: Find longest common subsequence (not necessarily contiguous)


🔧 Step 0: Define DP State
===========================
dp[i][j] = LCS length of text1[0:i] and text2[0:j]

Recurrence:
if text1[i-1] == text2[j-1]:
    dp[i][j] = 1 + dp[i-1][j-1]  ← Characters match!
else:
    dp[i][j] = max(dp[i-1][j], dp[i][j-1])  ← Skip from one


🔧 Step 1: Initialize DP Table
================================
      ""  a  c  e
   ┌───┬──┬──┬──┐
"" │ 0 │0 │0 │0 │  ← Base case: empty string
   ├───┼──┼──┼──┤
a  │ 0 │? │? │? │
   ├───┼──┼──┼──┤
b  │ 0 │? │? │? │
   ├───┼──┼──┼──┤
c  │ 0 │? │? │? │
   ├───┼──┼──┼──┤
d  │ 0 │? │? │? │
   ├───┼──┼──┼──┤
e  │ 0 │? │? │? │
   └───┴──┴──┴──┘
   ↑
Base case: empty string


🔄 Step 2: Fill Row 1 (text1[^0]='a')
=====================================
      ""  a  c  e
   ┌───┬──┬──┬──┐
"" │ 0 │0 │0 │0 │
   ├───┼──┼──┼──┤
a  │ 0 │1 │1 │1 │  ← 'a' matches at j=1
   └───┴──┴──┴──┘
        ↑  └──┘
      Match  Carry forward

[^1][^1]: 'a'=='a' ✅ → 1 + dp[^0][^0] = 1
[^1][^2]: 'a'!='c' ❌ → max(dp[^0][^2], dp[^1][^1]) = 1
[^1][^3]: 'a'!='e' ❌ → max(dp[^0][^3], dp[^1][^2]) = 1


🔄 Step 3: Fill Row 2 (text1[^1]='b')
=====================================
      ""  a  c  e
   ┌───┬──┬──┬──┐
"" │ 0 │0 │0 │0 │
   ├───┼──┼──┼──┤
a  │ 0 │1 │1 │1 │
   ├───┼──┼──┼──┤
b  │ 0 │1 │1 │1 │  ← No new matches
   └───┴──┴──┴──┘

[^2][^1]: 'b'!='a' ❌ → max(dp[^1][^1], dp[^2][^0]) = 1
[^2][^2]: 'b'!='c' ❌ → max(dp[^1][^2], dp[^2][^1]) = 1
[^2][^3]: 'b'!='e' ❌ → max(dp[^1][^3], dp[^2][^2]) = 1


🔄 Step 4: Fill Row 3 (text1[^2]='c')
=====================================
      ""  a  c  e
   ┌───┬──┬──┬──┐
"" │ 0 │0 │0 │0 │
   ├───┼──┼──┼──┤
a  │ 0 │1 │1 │1 │
   ├───┼──┼──┼──┤
b  │ 0 │1 │1 │1 │
   ├───┼──┼──┼──┤
c  │ 0 │1 │2 │2 │  ← 'c' matches at j=2!
   └───┴──┴──┴──┘
           ↑  └┘
         Match Carry

[^3][^1]: 'c'!='a' ❌ → max(dp[^2][^1], dp[^3][^0]) = 1
[^3][^2]: 'c'=='c' ✅ → 1 + dp[^2][^1] = 2
[^3][^3]: 'c'!='e' ❌ → max(dp[^2][^3], dp[^3][^2]) = 2


🔄 Step 5: Fill Row 4 (text1[^3]='d')
=====================================
      ""  a  c  e
   ┌───┬──┬──┬──┐
"" │ 0 │0 │0 │0 │
   ├───┼──┼──┼──┤
a  │ 0 │1 │1 │1 │
   ├───┼──┼──┼──┤
b  │ 0 │1 │1 │1 │
   ├───┼──┼──┼──┤
c  │ 0 │1 │2 │2 │
   ├───┼──┼──┼──┤
d  │ 0 │1 │2 │2 │  ← No new matches
   └───┴──┴──┴──┘


🔄 Step 6: Fill Row 5 (text1[^4]='e')
=====================================
      ""  a  c  e
   ┌───┬──┬──┬──┐
"" │ 0 │0 │0 │0 │
   ├───┼──┼──┼──┤
a  │ 0 │1 │1 │1 │
   ├───┼──┼──┼──┤
b  │ 0 │1 │1 │1 │
   ├───┼──┼──┼──┤
c  │ 0 │1 │2 │2 │
   ├───┼──┼──┼──┤
d  │ 0 │1 │2 │2 │
   ├───┼──┼──┼──┤
e  │ 0 │1 │2 │3 │  ← 'e' matches at j=3!
   └───┴──┴──┴──┘
                ↑
             ANSWER

[^5][^3]: 'e'=='e' ✅ → 1 + dp[^4][^2] = 3


🏆 Final Result
===============
LCS Length: 3
LCS String: "ace" ✅


📊 Visual Trace of Matches
===========================
text1: a b c d e
       ↓   ↓   ↓
text2: a   c   e

Matches form subsequence: a → c → e


⏰ Complexity Analysis
======================
Time: O(m × n) - Fill m×n table
Space: O(m × n) - DP table
Can optimize to O(n) using rolling array!
```


***

## 1️⃣3️⃣ **Master Problem Set**

### 🎯 Comprehensive Problem List by Pattern

| Problem | Difficulty | Key Technique | LC \# |
| :-- | :-- | :-- | :-- |
| **Fibonacci Number** | 🟢 Easy | Linear 1D | 509 |
| **Climbing Stairs** | 🟢 Easy | Linear 1D | 70 |
| **Min Cost Climbing Stairs** | 🟢 Easy | Linear 1D | 746 |
| **House Robber** | 🟡 Medium | Linear 1D | 198 |
| **Pascal's Triangle** | 🟢 Easy | 2D DP | 118 |
| **Unique Paths** | 🟡 Medium | Grid Path 2D | 62 |
| **Minimum Path Sum** | 🟡 Medium | Grid Path 2D | 64 |
| **Coin Change** | 🟡 Medium | Unbounded Knapsack | 322 |
| **Coin Change II** | 🟡 Medium | Unbounded Knapsack | 518 |
| **Partition Equal Subset Sum** | 🟡 Medium | 0/1 Knapsack | 416 |
| **Target Sum** | 🟡 Medium | 0/1 Knapsack | 494 |
| **Longest Common Subsequence** | 🟡 Medium | LCS Pattern | 1143 |
| **Edit Distance** | 🔴 Hard | LCS Pattern | 72 |
| **Longest Increasing Subsequence** | 🟡 Medium | Sequence DP | 300 |
| **Longest Palindromic Substring** | 🟡 Medium | Interval DP | 5 |
| **Palindrome Partitioning II** | 🔴 Hard | Interval DP | 132 |
| **Word Break** | 🟡 Medium | Linear DP + Hash | 139 |
| **Decode Ways** | 🟡 Medium | Linear 1D | 91 |
| **Unique Binary Search Trees** | 🟡 Medium | Catalan Numbers | 96 |
| **Maximum Subarray** | 🟡 Medium | Kadane's Algorithm | 53 |
| **Best Time to Buy/Sell Stock** | 🟢 Easy | State Machine | 121 |
| **Best Time Buy/Sell II** | 🟡 Medium | State Machine | 122 |
| **Best Time Buy/Sell III** | 🔴 Hard | State Machine | 123 |
| **Best Time Buy/Sell with Cooldown** | 🟡 Medium | State Machine | 309 |
| **House Robber II** | 🟡 Medium | Linear 1D (circular) | 213 |
| **House Robber III** | 🟡 Medium | Tree DP | 337 |
| **Maximal Square** | 🟡 Medium | 2D DP | 221 |
| **Perfect Squares** | 🟡 Medium | Unbounded Knapsack | 279 |
| **Triangle** | 🟡 Medium | Grid Path 2D | 120 |
| **Minimum Falling Path Sum** | 🟡 Medium | Grid Path 2D | 931 |
| **Longest Palindromic Subsequence** | 🟡 Medium | Interval DP | 516 |
| **Distinct Subsequences** | 🔴 Hard | LCS Pattern | 115 |
| **Interleaving String** | 🟡 Medium | 2D DP | 97 |
| **Scramble String** | 🔴 Hard | Interval DP | 87 |
| **Burst Balloons** | 🔴 Hard | Interval DP | 312 |
| **Stone Game** | 🟡 Medium | Interval DP | 877 |
| **Partition to K Equal Sum Subsets** | 🟡 Medium | Backtracking + DP | 698 |
| **Regular Expression Matching** | 🔴 Hard | 2D DP | 10 |
| **Wildcard Matching** | 🔴 Hard | 2D DP | 44 |

### 🎓 Study Path by Difficulty

**🟢 Beginner Level (Foundation):**

1. Fibonacci Number (LC 509)
2. Climbing Stairs (LC 70)
3. Min Cost Climbing Stairs (LC 746)
4. Best Time to Buy/Sell Stock (LC 121)
5. Pascal's Triangle (LC 118)

**🟡 Intermediate Level (Build Skills):**
6. House Robber (LC 198)
7. Coin Change (LC 322)
8. Unique Paths (LC 62)
9. Longest Common Subsequence (LC 1143)
10. Maximum Subarray (LC 53)
11. Word Break (LC 139)
12. Partition Equal Subset Sum (LC 416)

**🔴 Advanced Level (Master Patterns):**
13. Edit Distance (LC 72)
14. Longest Increasing Subsequence (LC 300)
15. Best Time Buy/Sell III (LC 123)
16. Palindrome Partitioning II (LC 132)
17. Burst Balloons (LC 312)
18. Regular Expression Matching (LC 10)

**🏆 Expert Level (FAANG Preparation):**
19. Distinct Subsequences (LC 115)
20. Scramble String (LC 87)
21. Interleaving String (LC 97)
22. Wildcard Matching (LC 44)

***

## 1️⃣4️⃣ **Memory Aids**

### 🧠 The DP Decision Framework

**D**efine the state clearly 📊
**Y**ield to base cases first 🎯
**N**avigate recurrence relations 🔄
**A**ccumulate results systematically 📈
**M**emoize or tabulate wisely 💾
**I**terate through all subproblems 🔁
**C**ompute final answer 🏆

**P**rune unnecessary space 🔧
**R**ecognize optimal substructure 🏗️
**O**verlapping? Use DP! 🎯
**G**row from small to large 📏
**R**eturn the stored solution ✅
**A**void recomputation always! ⚡
**M**aster the patterns 🎪

### 📐 Essential Formulas \& Recurrences

```
🎯 LINEAR DP:
dp[i] = f(dp[i-1], dp[i-2], ..., arr[i])

Example - Fibonacci:
dp[i] = dp[i-1] + dp[i-2]

Example - House Robber:
dp[i] = max(nums[i] + dp[i-2], dp[i-1])


🎯 0/1 KNAPSACK:
dp[i][w] = max(
    dp[i-1][w],                    // Don't take
    value[i] + dp[i-1][w-weight[i]] // Take (if fits)
)

Space optimized (iterate backwards):
for i in items:
    for w in range(W, weight[i]-1, -1):
        dp[w] = max(dp[w], value[i] + dp[w-weight[i]])


🎯 UNBOUNDED KNAPSACK:
dp[w] = max(dp[w], value[i] + dp[w-weight[i]])

Space optimized (iterate forwards):
for w in range(W+1):
    for i in items:
        if weight[i] <= w:
            dp[w] = max(dp[w], value[i] + dp[w-weight[i]])


🎯 LCS PATTERN:
if s1[i-1] == s2[j-1]:
    dp[i][j] = 1 + dp[i-1][j-1]
else:
    dp[i][j] = max(dp[i-1][j], dp[i][j-1])


🎯 GRID PATH:
dp[i][j] = grid[i][j] + min/max(dp[i-1][j], dp[i][j-1])


🎯 INTERVAL DP:
for length in range(2, n+1):
    for start in range(n-length+1):
        end = start + length - 1
        for split in range(start, end):
            dp[start][end] = optimal(
                dp[start][split],
                dp[split+1][end]
            )
```


### 🎪 Pattern Recognition Cheat Sheet

```
╔═══════════════════════════════════════════════╗
║         🎯 DP PATTERN QUICK REFERENCE          ║
╠═══════════════════════════════════════════════╣
║ 📏 LINEAR 1D:                                  ║
║   Signal: "each position", "sequential"       ║
║   State: dp[i] = solution at position i       ║
║   Examples: Stairs, Robber, Decode            ║
║                                               ║
║ 🎒 KNAPSACK:                                   ║
║   Signal: "capacity", "include/exclude"       ║
║   State: dp[i][w] = solution with capacity w  ║
║   Examples: Partition, Target Sum, Coin       ║
║                                               ║
║ 📝 LCS:                                        ║
║   Signal: "two sequences", "common"           ║
║   State: dp[i][j] = solution for s1[0:i],s2[0:j] ║
║   Examples: Edit Distance, LCS, Delete Ops    ║
║                                               ║
║ 🗺️ GRID PATH:                                  ║
║   Signal: "matrix", "paths", "grid"           ║
║   State: dp[i][j] = solution at cell (i,j)    ║
║   Examples: Unique Paths, Min Path Sum        ║
║                                               ║
║ 🔄 INTERVAL:                                   ║
║   Signal: "subarray", "range", "burst"        ║
║   State: dp[i][j] = solution for range [i,j]  ║
║   Examples: Burst Balloons, Palindrome        ║
╚═══════════════════════════════════════════════╝
```


### 💡 Complexity Quick Reference

| Pattern | Typical Time | Typical Space | Optimizable to |
| :-- | :-- | :-- | :-- |
| Linear 1D | O(n) | O(n) | O(1) ✅ |
| 0/1 Knapsack | O(n × W) | O(n × W) | O(W) ✅ |
| Unbounded Knapsack | O(n × W) | O(W) | - |
| LCS | O(m × n) | O(m × n) | O(n) ✅ |
| Grid Path | O(m × n) | O(m × n) | O(n) ✅ |
| Interval | O(n³) | O(n²) | - |
| Tree DP | O(n) | O(h) | - |

### 🎯 Interview Day Mnemonics

**Before coding:**

1. ✅ **S**tate - What does dp[i] mean?
2. ✅ **B**ase - What are the simplest cases?
3. ✅ **R**ecurrence - How do I build larger from smaller?
4. ✅ **O**rder - What order to fill the table?
5. ✅ **A**nswer - Where is the final answer?

**During coding:**

- "Index or Value?" - Am I using i or arr[i]?
- "Size n or n+1?" - Do I need dp[n]?
- "Range inclusive?" - Is it range(n) or range(n+1)?
- "Backwards or Forwards?" - 0/1 backwards, unbounded forwards
- "One or two indices?" - 1D or 2D problem?

**Common mantras:**

- 🎯 "dp size = n+1, range to n+1, return dp[n]"
- 🎯 "String indices: i-1 and j-1 in the recurrence"
- 🎯 "Knapsack 0/1: iterate capacity backwards"
- 🎯 "LCS match: diagonal+1, no match: max(top, left)"
- 🎯 "Grid: current = current + min/max(top, left)"

***

## 🎓 Final Words

**Dynamic Programming** is the cornerstone of algorithmic problem-solving and one of the most tested patterns in technical interviews. Master these core techniques:

1. 📏 **Linear 1D DP** - Sequential decisions (Fibonacci, House Robber)
2. 🎒 **Knapsack (0/1 \& Unbounded)** - Include/exclude with constraints
3. 📝 **LCS Pattern** - Comparing two sequences (Edit Distance, LCS)
4. 🗺️ **Grid Path 2D** - Matrix navigation and optimization
5. 🔄 **Interval DP** - Processing ranges and subarrays
6. 🤖 **State Machine** - Multiple states with transitions
7. 🌳 **Tree DP** - Recursion on tree structures

### 🎯 The Path to Mastery:

**Week 1-2: Foundations**

- Master linear 1D problems (Fibonacci, Stairs, House Robber)
- Understand memoization vs tabulation
- Practice space optimization

**Week 3-4: Core Patterns**

- Knapsack variations (0/1, unbounded, subset sum)
- LCS and edit distance problems
- Grid path problems

**Week 5-6: Advanced Techniques**

- Interval DP (palindromes, burst balloons)
- State machine DP (stock problems)
- Complex 2D DP

**Week 7-8: Interview Preparation**

- Mix of all patterns
- Time-constrained practice
- Mock interviews


### 🚀 Success Strategies:

✅ **Pattern Recognition** - Learn to identify DP signals instantly
✅ **State Definition** - Master the art of defining clear DP states
✅ **Recurrence Relations** - Practice deriving them from problem constraints
✅ **Edge Cases** - Always handle n=0, n=1, empty inputs
✅ **Space Optimization** - Know when and how to optimize
✅ **Clear Communication** - Explain your thought process step-by-step

### 💪 You've Got This!

Dynamic Programming transforms impossible-looking problems into elegant solutions. With consistent practice, you'll develop the intuition to:

- Recognize DP problems in seconds ⚡
- Define optimal states naturally 🎯
- Derive recurrence relations effortlessly 🔄
- Code solutions cleanly and bug-free ✅

**Remember:** Every DP expert started where you are now. The difference? They practiced consistently, learned from mistakes, and never gave up. Your DP mastery journey starts today! 🌟

***

*"From small solutions, build great answers. That's the DP way!"* 🔄✨💯

<div align="center">⁂</div>

[^1]: https://academic.oup.com/bioinformatics/article/doi/10.1093/bioinformatics/btac757/6847088

[^2]: https://www.opastpublishers.com/open-access-articles/qrgb-advanced-qr-code-generator-with-rgb-color-method-in-python-to-expand-data-capacity.pdf

