<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [🪟 The Sliding Window Pattern - Complete Interview Guide](#-the-sliding-window-pattern---complete-interview-guide)
  - [1️⃣ **Pattern Overview**](#-pattern-overview)
    - [🎯 Core Concept](#-core-concept)
    - [🎪 When to Use This Pattern](#-when-to-use-this-pattern)
    - [⏱️ Complexity Overview](#-complexity-overview)
  - [2️⃣ **Pattern Recognition \& Detection**](#-pattern-recognition-%5C-detection)
    - [🔍 Key Problem Signals](#-key-problem-signals)
    - [🎨 Visual Pattern Recognition](#-visual-pattern-recognition)
    - [📊 Pattern Detection Flowchart](#-pattern-detection-flowchart)
    - [🎭 Two Main Window Types](#-two-main-window-types)
  - [3️⃣ **Standard Algorithm Template**](#-standard-algorithm-template)
    - [🎯 Universal Sliding Window Template](#-universal-sliding-window-template)
    - [📝 Fixed Window Template (Simpler Version)](#-fixed-window-template-simpler-version)
  - [4️⃣ **Common Interview Problem Types**](#-common-interview-problem-types)
    - [🎯 Essential Problems Every Candidate Should Know](#-essential-problems-every-candidate-should-know)
  - [5️⃣ **Advanced Techniques \& Variations**](#-advanced-techniques-%5C-variations)
  - [🔬 Technique 1: Fixed-Size Window](#-technique-1-fixed-size-window)
    - [📋 When to Use](#-when-to-use)
    - [🎯 Core Implementation](#-core-implementation)
    - [📊 Visual Step-by-Step Walkthrough](#-visual-step-by-step-walkthrough)
    - [💻 Complete Problem Solutions](#-complete-problem-solutions)
      - [**Problem 1: Maximum Average Subarray (LC 643)**](#problem-1-maximum-average-subarray-lc-643)
      - [**Problem 2: Max Consecutive Ones III (LC 1004)**](#problem-2-max-consecutive-ones-iii-lc-1004)
      - [**Problem 3: Contains Duplicate II (LC 219)**](#problem-3-contains-duplicate-ii-lc-219)
      - [**Problem 4: Number of Sub-arrays of Size K (LC 1343)**](#problem-4-number-of-sub-arrays-of-size-k-lc-1343)
    - [🎯 Fixed-Size Window Problem List](#-fixed-size-window-problem-list)
  - [🔬 Technique 2: Dynamic Window - Longest Substring Type](#-technique-2-dynamic-window---longest-substring-type)
    - [📋 When to Use](#-when-to-use-1)
    - [🎯 Core Implementation](#-core-implementation-1)
    - [📊 Visual Execution Flow](#-visual-execution-flow)
    - [💻 Complete Problem Solutions](#-complete-problem-solutions-1)
      - [**Problem 1: Longest Substring Without Repeating Characters (LC 3)**](#problem-1-longest-substring-without-repeating-characters-lc-3)
      - [**Problem 2: Longest Substring with At Most K Distinct Characters (LC 340)**](#problem-2-longest-substring-with-at-most-k-distinct-characters-lc-340)
      - [**Problem 3: Longest Repeating Character Replacement (LC 424)**](#problem-3-longest-repeating-character-replacement-lc-424)
      - [**Problem 4: Max Consecutive Ones II (LC 487)**](#problem-4-max-consecutive-ones-ii-lc-487)
    - [🎯 Longest Substring Problem List](#-longest-substring-problem-list)
  - [🔬 Technique 3: Dynamic Window - Shortest Substring Type](#-technique-3-dynamic-window---shortest-substring-type)
    - [📋 When to Use](#-when-to-use-2)
    - [🎯 Core Implementation](#-core-implementation-2)
    - [📊 Visual Execution Flow](#-visual-execution-flow-1)
    - [💻 Complete Problem Solutions](#-complete-problem-solutions-2)
      - [**Problem 1: Minimum Window Substring (LC 76)**](#problem-1-minimum-window-substring-lc-76)
      - [**Problem 2: Minimum Size Subarray Sum (LC 209)**](#problem-2-minimum-size-subarray-sum-lc-209)
      - [**Problem 3: Minimum Window Subsequence (LC 727)**](#problem-3-minimum-window-subsequence-lc-727)
      - [**Problem 4: Smallest Subarray with Sum Greater Than Target (Variable)**](#problem-4-smallest-subarray-with-sum-greater-than-target-variable)
    - [🎯 Shortest Substring Problem List](#-shortest-substring-problem-list)
  - [🔬 Technique 4: String Matching / Permutation Window](#-technique-4-string-matching--permutation-window)
    - [📋 When to Use](#-when-to-use-3)
    - [🎯 Core Implementation](#-core-implementation-3)
    - [📊 Visual Execution Flow](#-visual-execution-flow-2)
    - [💻 Complete Problem Solutions](#-complete-problem-solutions-3)
      - [**Problem 1: Permutation in String (LC 567)**](#problem-1-permutation-in-string-lc-567)
      - [**Problem 2: Find All Anagrams in String (LC 438)**](#problem-2-find-all-anagrams-in-string-lc-438)
      - [**Problem 3: Substring with Concatenation of All Words (LC 30)**](#problem-3-substring-with-concatenation-of-all-words-lc-30)
      - [**Problem 4: Repeated DNA Sequences (LC 187)**](#problem-4-repeated-dna-sequences-lc-187)
    - [🎯 String Matching Problem List](#-string-matching-problem-list)
  - [6️⃣ **Comprehensive Comparison Table**](#-comprehensive-comparison-table)
  - [7️⃣ **Problem-to-Approach Mapping**](#-problem-to-approach-mapping)
  - [8️⃣ **Performance Characteristics**](#-performance-characteristics)
  - [9️⃣ **Selection Decision Tree**](#-selection-decision-tree)
  - [🔟 **Common Pitfalls Analysis**](#-common-pitfalls-analysis)
    - [🚨 Critical Bug Example: Off-by-One in Fixed Window](#-critical-bug-example-off-by-one-in-fixed-window)
      - [❌ WRONG CODE (with bugs):](#-wrong-code-with-bugs)
    - [📊 Execution Trace - WRONG vs EXPECTED:](#-execution-trace---wrong-vs-expected)
    - [🔬 Detailed Bug Breakdown:](#-detailed-bug-breakdown)
    - [✅ CORRECT CODE Comparison:](#-correct-code-comparison)
    - [🎯 Key Takeaways from Bug Analysis:](#-key-takeaways-from-bug-analysis)
  - [1️⃣1️⃣ **Interview Success Tips**](#-interview-success-tips)
    - [🎯 Problem Recognition Signals](#-problem-recognition-signals)
    - [🎪 Optimization Strategy Table](#-optimization-strategy-table)
    - [🚨 Common Edge Cases with Code Examples](#-common-edge-cases-with-code-examples)
      - [**1️⃣ Empty or Small Input**](#-empty-or-small-input)
      - [**2️⃣ Single Element Window**](#-single-element-window)
      - [**3️⃣ All Elements Same**](#-all-elements-same)
      - [**4️⃣ Window Equals Array Length**](#-window-equals-array-length)
      - [**5️⃣ Negative Numbers / Special Values**](#-negative-numbers--special-values)
    - [✅ Debug Checklist](#-debug-checklist)
    - [💡 Interview Communication Tips](#-interview-communication-tips)
  - [1️⃣2️⃣ **ASCII Problem Solving Flow**](#-ascii-problem-solving-flow)
    - [🎯 Sample Problem: Find Maximum Sum Subarray of Size K](#-sample-problem-find-maximum-sum-subarray-of-size-k)
    - [🎭 Sample Problem 2: Longest Substring Without Repeating Characters](#-sample-problem-2-longest-substring-without-repeating-characters)
  - [1️⃣3️⃣ **Master Problem Set**](#-master-problem-set)
    - [🎯 Comprehensive Problem List by Difficulty](#-comprehensive-problem-list-by-difficulty)
    - [🎓 Study Path by Experience Level](#-study-path-by-experience-level)
  - [1️⃣4️⃣ **Memory Aids**](#-memory-aids)
    - [🎯 Memorable Mnemonics](#-memorable-mnemonics)
    - [📐 Key Formulas \& Conditions](#-key-formulas-%5C-conditions)
    - [🧠 Pattern-Specific Reminders](#-pattern-specific-reminders)
    - [🎪 Quick Reference Card](#-quick-reference-card)
    - [💡 Interview Day Reminders](#-interview-day-reminders)
  - [🎓 Final Words](#-final-words)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# 🪟 The Sliding Window Pattern - Complete Interview Guide

## 1️⃣ **Pattern Overview**

### 🎯 Core Concept

**Input → Process → Output Flow:**

```
Input: Array/String + Window Size/Condition
   ↓
Process: Move window across array, track state
   ↓
Output: Optimal subarray/substring result
```

The **Sliding Window** pattern is a technique that reduces nested loops to a single pass through an array or string by maintaining a "window" of elements and sliding it across the data structure. Think of it like viewing scenery through a train window 🚂—you see different views as the window moves!

### 🎪 When to Use This Pattern

✅ **Use Sliding Window when:**

- Problem involves contiguous subarrays or substrings
- Need to find optimal (min/max/longest/shortest) subarray
- Working with sequential data and a window constraint
- Can efficiently add/remove elements from window state
- Brute force would require nested loops (O(n²) → O(n))

❌ **Don't use when:**

- Need non-contiguous elements
- Order doesn't matter
- Problem requires backtracking
- Window size can't be efficiently maintained


### ⏱️ Complexity Overview

| Metric | Typical Complexity | Explanation |
| :-- | :-- | :-- |
| **Time** | O(n) | Each element visited at most twice (enter \& exit window) |
| **Space** | O(1) to O(k) | Constant for counters, O(k) for hash maps tracking window state |
| **Optimization** | O(n²) → O(n) | Eliminates nested loops by reusing previous window computation |


***

## 2️⃣ **Pattern Recognition \& Detection**

### 🔍 Key Problem Signals

| Signal | Example Keywords | Pattern Type |
| :-- | :-- | :-- |
| 🎯 **Contiguous Elements** | "subarray", "substring", "consecutive" | Core indicator |
| 📏 **Size Constraint** | "length k", "at most k", "exactly k" | Fixed/Dynamic window |
| 🏆 **Optimization Goal** | "maximum", "minimum", "longest", "shortest" | Need to track optimal |
| 🔢 **Sequential Data** | Array, string, linked list | Linear traversal |
| 📊 **Aggregate Property** | "sum", "product", "distinct", "frequency" | Window state tracking |

### 🎨 Visual Pattern Recognition

```
Problem Type Identifier:
========================

📋 "Find the LONGEST substring with at most K distinct characters"
    ↓      ↓                        ↓              ↓
    🎯   Optimization             Constraint    Contiguous
    
✅ SLIDING WINDOW! ✅

Why? 
1. Contiguous (substring) ✓
2. Optimization goal (longest) ✓  
3. Constraint to maintain (K distinct) ✓
4. Can add/remove chars efficiently ✓
```


### 📊 Pattern Detection Flowchart

```
                    🤔 Problem Analysis Start
                              |
                    ┌─────────┴─────────┐
                    │ Contiguous data?  │
                    └─────────┬─────────┘
                              |
                    ┌─────────┴─────────┐
                    | YES ✅           NO ❌
                    ↓                    ↓
          ┌─────────────────┐      Use different pattern
          │ Has constraint? │      (Two Pointers, DP, etc.)
          └─────────┬───────┘
                    |
          ┌─────────┴─────────┐
          | YES ✅           NO ❌
          ↓                    ↓
    ┌──────────────┐     Maybe Prefix Sum
    │ SLIDING      │     or simple iteration
    │ WINDOW! 🎯   │
    └──────────────┘
```


### 🎭 Two Main Window Types

```
Type 1: FIXED SIZE WINDOW 📏
================================
Window size = K (constant)

[1, 2, 3, 4, 5, 6, 7]
 └──K──┘              Initial window
    └──K──┘           Slide right by 1
       └──K──┘        Keep sliding...


Type 2: DYNAMIC SIZE WINDOW 🔄
================================
Window size = Variable (based on condition)

[1, 2, 3, 4, 5, 6, 7]
 └┘                   Window expands...
 └──┘                 if condition met
 └─────┘              or shrinks...
    └──┘              if condition violated
```


***

## 3️⃣ **Standard Algorithm Template**

### 🎯 Universal Sliding Window Template

```python
def sliding_window_template(arr, condition):
    """
    🎯 Universal Sliding Window Template
    Works for 90% of sliding window problems!
    """
    # 1️⃣ Initialize window boundaries and state
    left = 0
    window_state = {}  # 📊 Track what's inside window (hash map, counter, sum, etc.)
    result = 0         # 🏆 Store optimal result
    
    # 2️⃣ Expand window by moving right pointer
    for right in range(len(arr)):
        # 🔄 Add new element to window state
        element = arr[right]
        window_state = update_state(window_state, element, action="add")
        
        # 3️⃣ Shrink window if condition violated
        while condition_violated(window_state):
            # 🔄 Remove leftmost element from window
            window_state = update_state(window_state, arr[left], action="remove")
            left += 1  # 👈 Shrink from left
        
        # 4️⃣ Update result if current window is valid
        result = update_result(result, window_state, right - left + 1)
    
    # 5️⃣ Return final result
    return result

# 🎪 Helper Functions (customize based on problem)
def update_state(state, element, action):
    """Update window state when adding/removing element"""
    pass

def condition_violated(state):
    """Check if window violates problem constraint"""
    pass

def update_result(result, state, window_size):
    """Update optimal result based on current window"""
    pass
```


### 📝 Fixed Window Template (Simpler Version)

```python
def fixed_window_template(arr, k):
    """
    📏 Fixed Size Sliding Window
    Window size = k (constant)
    """
    # 1️⃣ Handle edge case
    if len(arr) < k:
        return None
    
    # 2️⃣ Build initial window
    window_sum = sum(arr[:k])  # 📊 Or any aggregate metric
    result = window_sum
    
    # 3️⃣ Slide window across array
    for i in range(k, len(arr)):
        # 🔄 Slide: Remove leftmost, add new right element
        window_sum = window_sum - arr[i - k] + arr[i]
        result = max(result, window_sum)  # 🏆 Update optimal
    
    return result
```


***

## 4️⃣ **Common Interview Problem Types**

### 🎯 Essential Problems Every Candidate Should Know

**1️⃣ Maximum Sum Subarray of Size K (LC 643)** - Find max sum of k consecutive elements - **Key insight**: Classic fixed window, maintain running sum

**2️⃣ Longest Substring Without Repeating Characters (LC 3)** - Find longest substring with all unique chars - **Key insight**: Dynamic window with hash set, shrink when duplicate found

**3️⃣ Minimum Window Substring (LC 76)** - Find smallest substring containing all target chars - **Key insight**: Expand to satisfy, shrink to optimize, use frequency maps

**4️⃣ Longest Substring with At Most K Distinct Characters (LC 340)** - Find longest substring with ≤k distinct chars - **Key insight**: Dynamic window with char frequency map, shrink when exceeds k

**5️⃣ Fruits Into Baskets (LC 904)** - Pick maximum fruits with at most 2 types - **Key insight**: Disguised "longest subarray with 2 distinct elements" problem

**6️⃣ Permutation in String (LC 567)** - Check if string contains permutation of pattern - **Key insight**: Fixed window matching char frequencies

***

## 5️⃣ **Advanced Techniques \& Variations**

## 🔬 Technique 1: Fixed-Size Window

### 📋 When to Use

- Window size is explicitly given (k elements)
- Need to process every possible k-length subarray
- Problem asks for "of size k" or "every k elements"


### 🎯 Core Implementation

```python
def fixed_size_window(arr, k):
    """
    📏 Fixed-Size Sliding Window Pattern
    
    Time: O(n) - single pass
    Space: O(1) - only window state
    """
    if not arr or len(arr) < k:
        return None
    
    # 1️⃣ Initialize first window [0, k)
    window_sum = 0
    for i in range(k):
        window_sum += arr[i]
    
    max_sum = window_sum  # 🏆 Track maximum
    
    # 2️⃣ Slide window from index k to end
    for i in range(k, len(arr)):
        # 🔄 Slide operation: -left +right
        window_sum = window_sum - arr[i - k] + arr[i]
        max_sum = max(max_sum, window_sum)
    
    return max_sum
```


### 📊 Visual Step-by-Step Walkthrough

```
Example: arr = [2, 1, 5, 1, 3, 2], k = 3
Goal: Find maximum sum of any 3 consecutive elements

Step 0: Initialize window [0, 3)
=============================
[2, 1, 5, 1, 3, 2]
 └──K──┘
 window_sum = 2 + 1 + 5 = 8 ✅
 max_sum = 8

Step 1: Slide to [1, 4)
=============================
[2, 1, 5, 1, 3, 2]
    └──K──┘
 Remove: 2  Add: 1
 window_sum = 8 - 2 + 1 = 7
 max_sum = 8 (unchanged)

Step 2: Slide to [2, 5)
=============================
[2, 1, 5, 1, 3, 2]
       └──K──┘
 Remove: 1  Add: 3
 window_sum = 7 - 1 + 3 = 9 🎯
 max_sum = 9 (updated!)

Step 3: Slide to [3, 6)
=============================
[2, 1, 5, 1, 3, 2]
          └──K──┘
 Remove: 5  Add: 2
 window_sum = 9 - 5 + 2 = 6
 max_sum = 9 (unchanged)

Final Result: 9 🏆
```


### 💻 Complete Problem Solutions

#### **Problem 1: Maximum Average Subarray (LC 643)**

```python
def findMaxAverage(nums, k):
    """
    🎯 Find contiguous subarray of length k with maximum average
    
    Example: nums = [1,12,-5,-6,50,3], k = 4
    Output: 12.75 (subarray [12,-5,-6,50])
    
    Time: O(n) | Space: O(1)
    """
    # 1️⃣ Calculate sum of first window
    current_sum = sum(nums[:k])
    max_sum = current_sum
    
    # 2️⃣ Slide window and track maximum sum
    for i in range(k, len(nums)):
        # 🔄 Slide: remove left, add right
        current_sum += nums[i] - nums[i - k]
        max_sum = max(max_sum, current_sum)
    
    # 3️⃣ Return average
    return max_sum / k

# 📊 Execution Trace
# nums = [1, 12, -5, -6, 50, 3], k = 4
# Window [1,12,-5,-6]:  sum=2,   avg=0.5
# Window [12,-5,-6,50]: sum=51 ✅ avg=12.75
# Window [-5,-6,50,3]:  sum=42,  avg=10.5
# Result: 12.75
```


#### **Problem 2: Max Consecutive Ones III (LC 1004)**

```python
def longestOnes(nums, k):
    """
    🎯 Find longest subarray of 1s after flipping at most k zeros
    
    Example: nums = [1,1,1,0,0,0,1,1,1,1,0], k = 2
    Output: 6 (flip 2 zeros to get [0,0,0,1,1,1,1,1,1])
    
    Time: O(n) | Space: O(1)
    """
    left = 0
    zero_count = 0
    max_length = 0
    
    # 🔄 Expand window with right pointer
    for right in range(len(nums)):
        # 📊 Track zeros in window
        if nums[right] == 0:
            zero_count += 1
        
        # 🚫 Shrink if too many zeros
        while zero_count > k:
            if nums[left] == 0:
                zero_count -= 1
            left += 1
        
        # 🏆 Update maximum length
        max_length = max(max_length, right - left + 1)
    
    return max_length

# 📊 Visual Trace
# nums = [1,1,1,0,0,0,1,1,1,1,0], k = 2
# 
# Window [1,1,1,0,0]:     zero_count=2 ✅, len=5
# Window [1,0,0,0]:       zero_count=3 ❌ → shrink
# Window [0,0,0,1,1,1,1]: zero_count=3 ❌ → shrink  
# Window [0,1,1,1,1]:     zero_count=1 ✅, len=5
# Window [1,1,1,1,0]:     zero_count=1 ✅, len=5
# Best: any window with 2 flips covering 6 elements
```


#### **Problem 3: Contains Duplicate II (LC 219)**

```python
def containsNearbyDuplicate(nums, k):
    """
    🎯 Check if array has duplicate within k distance
    
    Example: nums = [1,2,3,1], k = 3
    Output: True (nums[^0] == nums[^3] and 3 - 0 = 3 ≤ k)
    
    Time: O(n) | Space: O(min(n, k))
    """
    window = set()  # 📊 Track elements in current window
    
    for i in range(len(nums)):
        # 🚫 Maintain window size ≤ k
        if i > k:
            window.remove(nums[i - k - 1])
        
        # ✅ Check for duplicate in window
        if nums[i] in window:
            return True
        
        # 🔄 Add current element
        window.add(nums[i])
    
    return False

# 📊 Execution Example
# nums = [1,2,3,1,2,3], k = 2
# 
# i=0: window={1}
# i=1: window={1,2}
# i=2: window={1,2,3}
# i=3: window={2,3,1} (removed nums[^0]=1, added nums[^3]=1)
# i=4: window={3,1,2} → 2 already exists! ✅ Return True
```


#### **Problem 4: Number of Sub-arrays of Size K (LC 1343)**

```python
def numOfSubarrays(arr, k, threshold):
    """
    🎯 Count subarrays of size k with average ≥ threshold
    
    Example: arr = [2,2,2,2,5,5,5,8], k = 3, threshold = 4
    Output: 3 (subarrays [2,5,5], [5,5,5], [5,5,8])
    
    Time: O(n) | Space: O(1)
    """
    # 🎯 Convert to sum comparison (avoid division)
    target_sum = k * threshold
    
    # 1️⃣ Initial window
    current_sum = sum(arr[:k])
    count = 1 if current_sum >= target_sum else 0
    
    # 2️⃣ Slide window
    for i in range(k, len(arr)):
        # 🔄 Update sum
        current_sum += arr[i] - arr[i - k]
        
        # ✅ Check threshold
        if current_sum >= target_sum:
            count += 1
    
    return count

# 📊 Visual Walkthrough
# arr = [2,2,2,2,5,5,5,8], k = 3, threshold = 4
# target_sum = 3 * 4 = 12
#
# [2,2,2]: sum=6  < 12 ❌
# [2,2,2]: sum=6  < 12 ❌
# [2,2,5]: sum=9  < 12 ❌
# [2,5,5]: sum=12 ≥ 12 ✅ count=1
# [5,5,5]: sum=15 ≥ 12 ✅ count=2
# [5,5,8]: sum=18 ≥ 12 ✅ count=3
# Result: 3
```


### 🎯 Fixed-Size Window Problem List

**1️⃣ Maximum Average Subarray I (LC 643)** - Find max average of k elements - **Key insight**: Track sum, divide by k at end

**2️⃣ Max Consecutive Ones III (LC 1004)** - Longest 1s after flipping k zeros - **Key insight**: Window with at most k zeros

**3️⃣ Grumpy Bookstore Owner (LC 1052)** - Maximize satisfied customers using k-minute power - **Key insight**: Fixed window on "grumpy" minutes to maximize gain

**4️⃣ Diet Plan Performance (LC 1176)** - Count periods where calorie sum meets threshold - **Key insight**: Fixed k-day window comparing to thresholds

**5️⃣ Defuse the Bomb (LC 1652)** - Decrypt code by summing next/previous k elements - **Key insight**: Circular array with fixed window

**6️⃣ K Radius Subarray Averages (LC 2090)** - Calculate average in radius k around each element - **Key insight**: Fixed window of size 2k+1

***

## 🔬 Technique 2: Dynamic Window - Longest Substring Type

### 📋 When to Use

- Need to find **longest/maximum** subarray/substring
- Problem has constraint like "at most k", "without repeating", "with condition"
- Goal is to **maximize** window size while satisfying constraint


### 🎯 Core Implementation

```python
def longest_substring_pattern(s, condition_param):
    """
    🎯 Dynamic Window - Maximize Window Size
    
    Template for "longest substring with constraint" problems
    Time: O(n) | Space: O(k) where k is unique elements in window
    """
    left = 0
    window_state = {}  # 📊 Hash map tracking window contents
    max_length = 0
    
    # 🔄 Expand window with right pointer
    for right in range(len(s)):
        # 1️⃣ Add right element to window
        char = s[right]
        window_state[char] = window_state.get(char, 0) + 1
        
        # 2️⃣ Shrink window while condition violated
        while condition_violated(window_state, condition_param):
            # 🔄 Remove left element
            window_state[s[left]] -= 1
            if window_state[s[left]] == 0:
                del window_state[s[left]]
            left += 1
        
        # 3️⃣ Update maximum (window is valid here)
        max_length = max(max_length, right - left + 1)
    
    return max_length
```


### 📊 Visual Execution Flow

```
Strategy: EXPAND first, SHRINK if needed, UPDATE result

Example: "Find longest substring with at most 2 distinct chars"
String: "e c e b a"

Step 1: Expand right=0
====================
[e] c e b a
 ↑
left=0, right=0
window={'e':1}, distinct=1 ✅
max_length=1

Step 2: Expand right=1  
====================
[e c] e b a
 ↑   ↑
left=0, right=1
window={'e':1,'c':1}, distinct=2 ✅
max_length=2

Step 3: Expand right=2
====================
[e c e] b a
 ↑     ↑
left=0, right=2
window={'e':2,'c':1}, distinct=2 ✅
max_length=3

Step 4: Expand right=3
====================
[e c e b] a
 ↑       ↑
left=0, right=3
window={'e':2,'c':1,'b':1}, distinct=3 ❌
Violates "at most 2 distinct"!

Shrink: Remove left
====================
e [c e b] a
   ↑     ↑
left=1, right=3
window={'c':1,'e':2,'b':1}, distinct=3 ❌ still bad

Shrink again:
====================
e c [e b] a
     ↑   ↑
left=2, right=3  
window={'e':1,'b':1}, distinct=2 ✅
max_length=3 (unchanged)

Step 5: Expand right=4
====================
e c [e b a]
     ↑     ↑
left=2, right=4
window={'e':1,'b':1,'a':1}, distinct=3 ❌

Shrink until valid:
====================
e c e [b a]
       ↑   ↑
left=3, right=4
window={'b':1,'a':1}, distinct=2 ✅
max_length=3 (unchanged)

Final Result: 3 🏆 (substring "ece")
```


### 💻 Complete Problem Solutions

#### **Problem 1: Longest Substring Without Repeating Characters (LC 3)**

```python
def lengthOfLongestSubstring(s):
    """
    🎯 Find length of longest substring without repeating characters
    
    Example: s = "abcabcbb"
    Output: 3 (substring "abc")
    
    Time: O(n) | Space: O(min(n, charset_size))
    """
    char_set = set()  # 📊 Track unique chars in window
    left = 0
    max_length = 0
    
    for right in range(len(s)):
        # 🚫 Shrink until no duplicates
        while s[right] in char_set:
            char_set.remove(s[left])
            left += 1
        
        # ✅ Add current character (window is valid)
        char_set.add(s[right])
        max_length = max(max_length, right - left + 1)
    
    return max_length

# 📊 Detailed Trace
# s = "pwwkew"
#
# right=0: [p], char_set={p}, max=1
# right=1: [pw], char_set={p,w}, max=2
# right=2: pw[w] → duplicate! shrink
#          [w], char_set={w}, max=2
# right=3: [wk], char_set={w,k}, max=2
# right=4: [wke], char_set={w,k,e}, max=3 ✅
# right=5: wke[w] → duplicate! shrink to [ew]
#          char_set={e,w}, max=3
# Result: 3 ("wke")
```


#### **Problem 2: Longest Substring with At Most K Distinct Characters (LC 340)**

```python
def lengthOfLongestSubstringKDistinct(s, k):
    """
    🎯 Find longest substring with at most k distinct characters
    
    Example: s = "eceba", k = 2
    Output: 3 (substring "ece")
    
    Time: O(n) | Space: O(k)
    """
    if k == 0:
        return 0
    
    char_count = {}  # 📊 Frequency map
    left = 0
    max_length = 0
    
    for right in range(len(s)):
        # 1️⃣ Add right character
        char = s[right]
        char_count[char] = char_count.get(char, 0) + 1
        
        # 2️⃣ Shrink if too many distinct chars
        while len(char_count) > k:
            left_char = s[left]
            char_count[left_char] -= 1
            if char_count[left_char] == 0:
                del char_count[left_char]
            left += 1
        
        # 3️⃣ Update maximum
        max_length = max(max_length, right - left + 1)
    
    return max_length

# 📊 Example Walkthrough
# s = "eceba", k = 2
#
# Window [e]:      {'e':1}, distinct=1, len=1
# Window [ec]:     {'e':1,'c':1}, distinct=2, len=2
# Window [ece]:    {'e':2,'c':1}, distinct=2, len=3 ✅
# Window [eceb]:   {'e':2,'c':1,'b':1}, distinct=3 ❌
#   Shrink → [ceb]: {'c':1,'e':1,'b':1}, distinct=3 ❌
#   Shrink → [eb]:  {'e':1,'b':1}, distinct=2, len=2
# Window [eba]:    {'e':1,'b':1,'a':1}, distinct=3 ❌
#   Shrink → [ba]: {'b':1,'a':1}, distinct=2, len=2
# Result: 3
```


#### **Problem 3: Longest Repeating Character Replacement (LC 424)**

```python
def characterReplacement(s, k):
    """
    🎯 Find longest substring with same char after at most k replacements
    
    Example: s = "AABABBA", k = 1
    Output: 4 (replace one 'A' to get "AAAA" or one 'B' to get "BBBB")
    
    Key Insight: window_length - max_frequency ≤ k
    (we can replace the minority characters)
    
    Time: O(n) | Space: O(26) = O(1)
    """
    char_count = {}
    left = 0
    max_length = 0
    max_freq = 0  # 🏆 Most frequent char in current window
    
    for right in range(len(s)):
        # 1️⃣ Add right character
        char = s[right]
        char_count[char] = char_count.get(char, 0) + 1
        max_freq = max(max_freq, char_count[char])
        
        # 2️⃣ Check if we need more than k replacements
        window_length = right - left + 1
        replacements_needed = window_length - max_freq
        
        # 🚫 Shrink if invalid
        if replacements_needed > k:
            char_count[s[left]] -= 1
            left += 1
        
        # 3️⃣ Update result (window is valid)
        max_length = max(max_length, right - left + 1)
    
    return max_length

# 📊 Visual Trace
# s = "AABABBA", k = 1
#
# [A]:        freq={'A':1}, maxFreq=1, need=0 ✅, len=1
# [AA]:       freq={'A':2}, maxFreq=2, need=0 ✅, len=2
# [AAB]:      freq={'A':2,'B':1}, maxFreq=2, need=1 ✅, len=3
# [AABA]:     freq={'A':3,'B':1}, maxFreq=3, need=1 ✅, len=4
# [AABAB]:    freq={'A':3,'B':2}, maxFreq=3, need=2 ❌
#   Shrink → [ABAB]: maxFreq=2, need=2 ❌
#   Shrink → [BAB]: freq={'A':1,'B':2}, maxFreq=2, need=1 ✅, len=3
# [BABB]:     freq={'A':1,'B':3}, maxFreq=3, need=1 ✅, len=4
# [BABBA]:    freq={'A':2,'B':3}, maxFreq=3, need=2 ❌
#   Shrink → [ABBA]: maxFreq=2, need=2 ❌
#   Shrink → [BBA]: freq={'A':1,'B':2}, maxFreq=2, need=1 ✅, len=3
# Result: 4
```


#### **Problem 4: Max Consecutive Ones II (LC 487)**

```python
def findMaxConsecutiveOnes(nums):
    """
    🎯 Find max consecutive 1s after flipping at most one 0
    
    Example: nums = [1,0,1,1,0]
    Output: 4 (flip nums[^1] → [1,1,1,1,0])
    
    Time: O(n) | Space: O(1)
    """
    left = 0
    zero_count = 0
    max_length = 0
    
    for right in range(len(nums)):
        # 📊 Count zeros in window
        if nums[right] == 0:
            zero_count += 1
        
        # 🚫 Shrink if more than 1 zero
        while zero_count > 1:
            if nums[left] == 0:
                zero_count -= 1
            left += 1
        
        # 🏆 Update maximum
        max_length = max(max_length, right - left + 1)
    
    return max_length

# 📊 Example
# nums = [1,0,1,1,0]
#
# [^1]:       zeros=0, len=1
# [1,0]:     zeros=1 ✅, len=2
# [1,0,1]:   zeros=1 ✅, len=3
# [1,0,1,1]: zeros=1 ✅, len=4 ✅ (best!)
# [1,0,1,1,0]: zeros=2 ❌
#   Shrink → [0,1,1,0]: zeros=2 ❌
#   Shrink → [1,1,0]: zeros=1 ✅, len=3
# Result: 4
```


### 🎯 Longest Substring Problem List

**1️⃣ Longest Substring Without Repeating Characters (LC 3)** - All unique chars - **Key insight**: Hash set to detect duplicates

**2️⃣ Longest Substring with At Most K Distinct (LC 340)** - At most k unique chars - **Key insight**: Frequency map, shrink when exceeds k

**3️⃣ Longest Repeating Character Replacement (LC 424)** - Same char after k replacements - **Key insight**: window_size - max_freq ≤ k

**4️⃣ Longest Substring with At Most Two Distinct (LC 159)** - At most 2 unique chars - **Key insight**: Special case of k=2

**5️⃣ Fruit Into Baskets (LC 904)** - Pick max fruits from 2 types - **Key insight**: Disguised k=2 distinct problem

**6️⃣ Max Consecutive Ones III (LC 1004)** - Longest 1s after flipping k zeros - **Key insight**: At most k zeros in window

***

## 🔬 Technique 3: Dynamic Window - Shortest Substring Type

### 📋 When to Use

- Need to find **shortest/minimum** subarray/substring
- Problem has requirement like "contains all", "sum ≥ target", "satisfies condition"
- Goal is to **minimize** window size while satisfying constraint


### 🎯 Core Implementation

```python
def shortest_substring_pattern(s, target_condition):
    """
    🎯 Dynamic Window - Minimize Window Size
    
    Template for "shortest substring satisfying constraint" problems
    Time: O(n) | Space: O(k)
    """
    left = 0
    window_state = {}
    min_length = float('inf')
    
    # 🔄 Expand window with right pointer
    for right in range(len(s)):
        # 1️⃣ Add right element to window
        element = s[right]
        window_state[element] = window_state.get(element, 0) + 1
        
        # 2️⃣ Shrink window while condition SATISFIED (opposite of longest!)
        while condition_satisfied(window_state, target_condition):
            # 🏆 Update minimum (window is valid)
            min_length = min(min_length, right - left + 1)
            
            # 🔄 Try to shrink further
            window_state[s[left]] -= 1
            if window_state[s[left]] == 0:
                del window_state[s[left]]
            left += 1
    
    return min_length if min_length != float('inf') else 0
```


### 📊 Visual Execution Flow

```
Strategy: EXPAND until valid, SHRINK while valid, UPDATE when shrinking

Example: "Find shortest substring containing all chars from target"
String: "a d o b e c o d e b a n c"
Target: "abc"

Step 1-5: Expand until we have all of "abc"
==========================================
[a d o b e c] o d e b a n c
 ↑           ↑
left=0, right=5
window={'a':1,'d':1,'o':1,'b':1,'e':1,'c':1}
Has 'a','b','c'? YES ✅
min_length = 6

Step 6: Shrink while still valid
================================
a [d o b e c] o d e b a n c
   ↑         ↑
left=1, right=5
Remove 'a', still has all "abc"? YES ✅
min_length = 5

Step 7: Shrink more
==================
a d [o b e c] o d e b a n c
     ↑       ↑
left=2, right=5
Remove 'd', still has all "abc"? YES ✅
min_length = 4

Step 8: Shrink more
==================
a d o [b e c] o d e b a n c
       ↑     ↑
left=3, right=5
Remove 'o', still has all "abc"? YES ✅
min_length = 3

Step 9: Try to shrink again
===========================
a d o b [e c] o d e b a n c
         ↑   ↑
left=4, right=5
Remove 'b', still has all "abc"? NO ❌
Window becomes invalid, stop shrinking

Step 10: Expand right to find next valid window
===============================================
Continue process...

Eventually find: [b a n c] at end with length 4
Final minimum: 3 ("bec" or "ebc")
```


### 💻 Complete Problem Solutions

#### **Problem 1: Minimum Window Substring (LC 76)**

```python
def minWindow(s, t):
    """
    🎯 Find minimum window in s containing all characters from t
    
    Example: s = "ADOBECODEBANC", t = "ABC"
    Output: "BANC"
    
    Time: O(m + n) where m=len(s), n=len(t)
    Space: O(k) where k=unique chars in t
    """
    if not s or not t:
        return ""
    
    # 📊 Frequency maps
    target_count = {}
    for char in t:
        target_count[char] = target_count.get(char, 0) + 1
    
    window_count = {}
    required = len(target_count)  # Unique chars needed
    formed = 0  # How many unique chars satisfied
    
    left = 0
    min_length = float('inf')
    result = (0, 0)  # (left, right) of best window
    
    for right in range(len(s)):
        # 1️⃣ Add character to window
        char = s[right]
        window_count[char] = window_count.get(char, 0) + 1
        
        # ✅ Check if this char requirement is satisfied
        if char in target_count and window_count[char] == target_count[char]:
            formed += 1
        
        # 2️⃣ Shrink while window is valid
        while left <= right and formed == required:
            # 🏆 Update result if smaller window found
            if right - left + 1 < min_length:
                min_length = right - left + 1
                result = (left, right)
            
            # 🔄 Try to shrink
            left_char = s[left]
            window_count[left_char] -= 1
            if left_char in target_count and window_count[left_char] < target_count[left_char]:
                formed -= 1
            left += 1
    
    # 3️⃣ Return result
    left_idx, right_idx = result
    return s[left_idx:right_idx + 1] if min_length != float('inf') else ""

# 📊 Detailed Trace
# s = "ADOBECODEBANC", t = "ABC"
# target_count = {'A':1, 'B':1, 'C':1}, required=3
#
# [ADOBEC]:      formed=3 ✅, len=6, result="ADOBEC"
#   Shrink → [DOBEC]: formed=2 ❌, stop shrinking
# [DOBECODEBA]:  formed=3 ✅, len=9
#   Shrink → [OBECODEBA]: formed=3 ✅, len=8
#   Shrink → [BECODEBA]: formed=3 ✅, len=7
#   Shrink → [ECODEBA]: formed=2 ❌, stop
# [ECODEBAN]:    formed=2
# [ECODEBANC]:   formed=3 ✅, len=8
#   Shrink → [CODEBANC]: formed=3 ✅, len=7
#   Shrink → [ODEBANC]: formed=3 ✅, len=6
#   Shrink → [DEBANC]: formed=3 ✅, len=5
#   Shrink → [EBANC]: formed=3 ✅, len=4
#   Shrink → [BANC]: formed=3 ✅, len=4 ✅ (best!)
#   Shrink → [ANC]: formed=2 ❌, stop
# Result: "BANC" (length 4)
```


#### **Problem 2: Minimum Size Subarray Sum (LC 209)**

```python
def minSubArrayLen(target, nums):
    """
    🎯 Find minimum length subarray with sum ≥ target
    
    Example: target = 7, nums = [2,3,1,2,4,3]
    Output: 2 (subarray [4,3])
    
    Time: O(n) | Space: O(1)
    """
    left = 0
    current_sum = 0
    min_length = float('inf')
    
    for right in range(len(nums)):
        # 1️⃣ Add element to window
        current_sum += nums[right]
        
        # 2️⃣ Shrink while condition satisfied
        while current_sum >= target:
            # 🏆 Update minimum
            min_length = min(min_length, right - left + 1)
            
            # 🔄 Try to shrink
            current_sum -= nums[left]
            left += 1
    
    return min_length if min_length != float('inf') else 0

# 📊 Visual Walkthrough
# target = 7, nums = [2,3,1,2,4,3]
#
# [^2]:         sum=2 < 7 ❌
# [2,3]:       sum=5 < 7 ❌
# [2,3,1]:     sum=6 < 7 ❌
# [2,3,1,2]:   sum=8 ≥ 7 ✅, len=4
#   Shrink → [3,1,2]: sum=6 < 7 ❌, stop
# [3,1,2,4]:   sum=10 ≥ 7 ✅, len=4
#   Shrink → [1,2,4]: sum=7 ≥ 7 ✅, len=3 (better!)
#   Shrink → [2,4]: sum=6 < 7 ❌, stop
# [2,4,3]:     sum=9 ≥ 7 ✅, len=3
#   Shrink → [4,3]: sum=7 ≥ 7 ✅, len=2 (best!) ✅
#   Shrink → [^3]: sum=3 < 7 ❌, stop
# Result: 2
```


#### **Problem 3: Minimum Window Subsequence (LC 727)**

```python
def minWindow(s, t):
    """
    🎯 Find minimum window in s containing t as SUBSEQUENCE
    
    Example: s = "abcdebdde", t = "bde"
    Output: "bcde" (shortest window containing b,d,e in order)
    
    Time: O(m * n) | Space: O(1)
    """
    m, n = len(s), len(t)
    
    # Two-pointer approach with special logic
    start = 0
    min_length = float('inf')
    result_start = 0
    
    while start < m:
        # 1️⃣ Forward pass: find end of window
        t_idx = 0
        end = start
        
        while end < m:
            if s[end] == t[t_idx]:
                t_idx += 1
                if t_idx == n:  # Found all chars of t
                    break
            end += 1
        
        if t_idx < n:  # Didn't find complete subsequence
            break
        
        # 2️⃣ Backward pass: shrink window from right
        t_idx = n - 1
        while t_idx >= 0:
            if s[end] == t[t_idx]:
                t_idx -= 1
            end -= 1
        
        end += 1  # Adjust to valid position
        
        # 🏆 Update result
        if end - start + 1 < min_length:
            min_length = end - start + 1
            result_start = start
        
        start = end + 1
    
    return s[result_start:result_start + min_length] if min_length != float('inf') else ""

# 📊 Example Trace
# s = "abcdebdde", t = "bde"
#
# Starting from index 0:
#   Forward: a[b]c[d][e] → found "bde" at indices 1,3,4
#   Backward: shrink from e to get [bcde]
#   Window: "bcde" (length 4) ✅
#
# Starting from index 5:
#   Forward: [b][d]d[e] → found "bde" at indices 5,6,8
#   Backward: shrink from e to get [bdde]
#   Window: "bdde" (length 4)
#
# Result: "bcde" (first occurrence with length 4)
```


#### **Problem 4: Smallest Subarray with Sum Greater Than Target (Variable)**

```python
def smallestSubarray(arr, target):
    """
    🎯 Find smallest subarray with sum > target (strictly greater)
    
    Example: arr = [1, 4, 45, 6, 0, 19], target = 51
    Output: 3 (subarray [4,45,6])
    
    Time: O(n) | Space: O(1)
    """
    left = 0
    current_sum = 0
    min_length = float('inf')
    
    for right in range(len(arr)):
        # 1️⃣ Expand window
        current_sum += arr[right]
        
        # 2️⃣ Shrink while sum > target
        while current_sum > target:
            # 🏆 Update minimum
            min_length = min(min_length, right - left + 1)
            
            # 🔄 Shrink
            current_sum -= arr[left]
            left += 1
    
    return min_length if min_length != float('inf') else -1

# 📊 Visual Example
# arr = [1, 4, 45, 6, 0, 19], target = 51
#
# [^1]:              sum=1 ≤ 51 ❌
# [1,4]:            sum=5 ≤ 51 ❌
# [1,4,45]:         sum=50 ≤ 51 ❌
# [1,4,45,6]:       sum=56 > 51 ✅, len=4
#   Shrink → [4,45,6]: sum=55 > 51 ✅, len=3 (better!) ✅
#   Shrink → [45,6]: sum=51 ≤ 51 ❌, stop
# [45,6,0]:         sum=51 ≤ 51 ❌
# [45,6,0,19]:      sum=70 > 51 ✅, len=4
#   Shrink → [6,0,19]: sum=25 ≤ 51 ❌, stop
# Result: 3
```


### 🎯 Shortest Substring Problem List

**1️⃣ Minimum Window Substring (LC 76)** - Shortest containing all target chars - **Key insight**: Shrink while all requirements met

**2️⃣ Minimum Size Subarray Sum (LC 209)** - Shortest with sum ≥ target - **Key insight**: Shrink while sum valid

**3️⃣ Minimum Window Subsequence (LC 727)** - Shortest containing target as subsequence - **Key insight**: Forward-backward two passes

**4️⃣ Smallest Range Covering Elements from K Lists (LC 632)** - Smallest range covering all lists - **Key insight**: Priority queue + sliding window

**5️⃣ Find All Anagrams in String (LC 438)** - All anagram positions - **Key insight**: Fixed window with frequency matching

**6️⃣ Substring with Concatenation of All Words (LC 30)** - Shortest containing all words - **Key insight**: Word-level sliding window

***

## 🔬 Technique 4: String Matching / Permutation Window

### 📋 When to Use

- Problem asks for **anagram**, **permutation**, or **exact character match**
- Need to find if one string contains permutation of another
- Fixed window size equals length of pattern
- Frequency matching is required


### 🎯 Core Implementation

```python
def permutation_window_pattern(s, pattern):
    """
    🎯 String Matching Window Pattern
    
    Check if s contains any permutation of pattern
    Time: O(n) | Space: O(k) where k=charset size
    """
    if len(pattern) > len(s):
        return False
    
    # 📊 Build frequency map of pattern
    pattern_count = {}
    for char in pattern:
        pattern_count[char] = pattern_count.get(char, 0) + 1
    
    # 📊 Build frequency map of first window
    window_count = {}
    window_size = len(pattern)
    
    for i in range(window_size):
        char = s[i]
        window_count[char] = window_count.get(char, 0) + 1
    
    # ✅ Check if first window matches
    if window_count == pattern_count:
        return True
    
    # 🔄 Slide window across remaining string
    for i in range(window_size, len(s)):
        # Remove left character
        left_char = s[i - window_size]
        window_count[left_char] -= 1
        if window_count[left_char] == 0:
            del window_count[left_char]
        
        # Add right character
        right_char = s[i]
        window_count[right_char] = window_count.get(right_char, 0) + 1
        
        # ✅ Check if current window matches
        if window_count == pattern_count:
            return True
    
    return False
```


### 📊 Visual Execution Flow

```
Example: Check if "eidbaooo" contains permutation of "ab"

Pattern: "ab"
pattern_count = {'a':1, 'b':1}

String: "e i d b a o o o"
         └─┘              Window size = 2

Step 1: Window [ei]
==================
window_count = {'e':1, 'i':1}
Compare: {'e':1,'i':1} ≠ {'a':1,'b':1} ❌

Step 2: Slide to [id]
==================
Remove 'e', Add 'd'
window_count = {'i':1, 'd':1}
Compare: {'i':1,'d':1} ≠ {'a':1,'b':1} ❌

Step 3: Slide to [db]
==================
Remove 'i', Add 'b'
window_count = {'d':1, 'b':1}
Compare: {'d':1,'b':1} ≠ {'a':1,'b':1} ❌

Step 4: Slide to [ba] 🎯
==================
Remove 'd', Add 'a'
window_count = {'b':1, 'a':1}
Compare: {'b':1,'a':1} = {'a':1,'b':1} ✅ MATCH!

Result: TRUE (found "ba" which is permutation of "ab")
```


### 💻 Complete Problem Solutions

#### **Problem 1: Permutation in String (LC 567)**

```python
def checkInclusion(s1, s2):
    """
    🎯 Check if s2 contains any permutation of s1
    
    Example: s1 = "ab", s2 = "eidbaooo"
    Output: True (s2 contains "ba" which is permutation of "ab")
    
    Time: O(n) | Space: O(1) - at most 26 lowercase letters
    """
    if len(s1) > len(s2):
        return False
    
    # 📊 Frequency maps
    s1_count = [^0] * 26
    window_count = [^0] * 26
    
    # Build frequency for s1 and first window
    for i in range(len(s1)):
        s1_count[ord(s1[i]) - ord('a')] += 1
        window_count[ord(s2[i]) - ord('a')] += 1
    
    # ✅ Check if first window matches
    matches = 0
    for i in range(26):
        if s1_count[i] == window_count[i]:
            matches += 1
    
    # 🔄 Slide window
    for i in range(len(s1), len(s2)):
        if matches == 26:  # All frequencies match!
            return True
        
        # Add right character
        right_idx = ord(s2[i]) - ord('a')
        window_count[right_idx] += 1
        if window_count[right_idx] == s1_count[right_idx]:
            matches += 1
        elif window_count[right_idx] == s1_count[right_idx] + 1:
            matches -= 1
        
        # Remove left character
        left_idx = ord(s2[i - len(s1)]) - ord('a')
        window_count[left_idx] -= 1
        if window_count[left_idx] == s1_count[left_idx]:
            matches += 1
        elif window_count[left_idx] == s1_count[left_idx] - 1:
            matches -= 1
    
    return matches == 26

# 📊 Optimized with Counter
from collections import Counter

def checkInclusion_v2(s1, s2):
    """Alternative implementation using Counter"""
    if len(s1) > len(s2):
        return False
    
    s1_count = Counter(s1)
    window_count = Counter(s2[:len(s1)])
    
    if window_count == s1_count:
        return True
    
    for i in range(len(s1), len(s2)):
        # Slide window
        right_char = s2[i]
        left_char = s2[i - len(s1)]
        
        window_count[right_char] += 1
        window_count[left_char] -= 1
        
        if window_count[left_char] == 0:
            del window_count[left_char]
        
        if window_count == s1_count:
            return True
    
    return False
```


#### **Problem 2: Find All Anagrams in String (LC 438)**

```python
def findAnagrams(s, p):
    """
    🎯 Find all start indices of p's anagrams in s
    
    Example: s = "cbaebabacd", p = "abc"
    Output: [0, 6] (substrings "cba" and "bac")
    
    Time: O(n) | Space: O(1)
    """
    if len(p) > len(s):
        return []
    
    result = []
    p_count = [^0] * 26
    window_count = [^0] * 26
    
    # Build frequency maps
    for i in range(len(p)):
        p_count[ord(p[i]) - ord('a')] += 1
        window_count[ord(s[i]) - ord('a')] += 1
    
    # Check first window
    if window_count == p_count:
        result.append(0)
    
    # Slide window
    for i in range(len(p), len(s)):
        # Add right, remove left
        window_count[ord(s[i]) - ord('a')] += 1
        window_count[ord(s[i - len(p)]) - ord('a')] -= 1
        
        # Check if anagram
        if window_count == p_count:
            result.append(i - len(p) + 1)
    
    return result

# 📊 Detailed Trace
# s = "cbaebabacd", p = "abc"
# p_count = [1,1,1,0,...,0]  (a=1, b=1, c=1)
#
# Window [cba]:  ✅ Match! → result=[^0]
# Window [bae]:  ❌
# Window [aeb]:  ❌
# Window [eba]:  ❌
# Window [bab]:  ❌
# Window [aba]:  ❌
# Window [bac]:  ✅ Match! → result=[0,6]
# Window [acd]:  ❌
# Result: [0, 6]
```


#### **Problem 3: Substring with Concatenation of All Words (LC 30)**

```python
def findSubstring(s, words):
    """
    🎯 Find starting indices where concatenation of all words exists
    
    Example: s = "barfoothefoobarman", words = ["foo","bar"]
    Output: [0, 9] ("barfoo" at 0, "foobar" at 9)
    
    Time: O(n * m * len(word)) | Space: O(m)
    """
    if not s or not words:
        return []
    
    word_len = len(words[^0])
    word_count = len(words)
    total_len = word_len * word_count
    
    if len(s) < total_len:
        return []
    
    # 📊 Build frequency map of words
    word_freq = {}
    for word in words:
        word_freq[word] = word_freq.get(word, 0) + 1
    
    result = []
    
    # 🔄 Try each starting position
    for i in range(len(s) - total_len + 1):
        # Build window of words
        seen = {}
        j = 0
        
        while j < word_count:
            word_start = i + j * word_len
            word = s[word_start:word_start + word_len]
            
            if word not in word_freq:
                break
            
            seen[word] = seen.get(word, 0) + 1
            
            if seen[word] > word_freq[word]:
                break
            
            j += 1
        
        # ✅ Check if all words matched
        if j == word_count:
            result.append(i)
    
    return result

# 📊 Example Walkthrough
# s = "barfoothefoobarman", words = ["foo","bar"]
# word_freq = {'foo':1, 'bar':1}
# word_len = 3, total_len = 6
#
# i=0: [bar][foo] → seen={'bar':1,'foo':1} = word_freq ✅ → result=[^0]
# i=1: [arf][oot] → 'arf' not in word_freq ❌
# i=2: [rfo][oth] → 'rfo' not in word_freq ❌
# ...continue checking...
# i=9: [foo][bar] → seen={'foo':1,'bar':1} = word_freq ✅ → result=[0,9]
# Result: [0, 9]
```


#### **Problem 4: Repeated DNA Sequences (LC 187)**

```python
def findRepeatedDnaSequences(s):
    """
    🎯 Find all 10-letter DNA sequences that occur more than once
    
    Example: s = "AAAAACCCCCAAAAACCCCCCAAAAAGGGTTT"
    Output: ["AAAAACCCCC", "CCCCCAAAAA"]
    
    Time: O(n) | Space: O(n)
    """
    if len(s) < 10:
        return []
    
    seen = set()
    repeated = set()
    
    # 🔄 Fixed window of size 10
    for i in range(len(s) - 9):
        sequence = s[i:i + 10]
        
        if sequence in seen:
            repeated.add(sequence)
        else:
            seen.add(sequence)
    
    return list(repeated)

# 📊 Visual Example
# s = "AAAAACCCCCAAAAACCCCCCAAAAAGGGTTT"
#
# Window [AAAAACCCCC]: Not seen → seen={'AAAAACCCCC'}
# Window [AAAACCCCCA]: Not seen → seen={...,'AAAACCCCCA'}
# Window [AAACCCCCAA]: Not seen → seen={...,'AAACCCCCAA'}
# Window [AACCCCCAAA]: Not seen → seen={...,'AACCCCCAAA'}
# Window [ACCCCCAAAA]: Not seen → seen={...,'ACCCCCAAAA'}
# Window [CCCCCAAAAA]: Not seen → seen={...,'CCCCCAAAAA'}
# Window [CCCCAAAAAC]: Not seen → seen={...,'CCCCAAAAAC'}
# Window [CCCAAAAAC C]: Not seen → seen={...,'CCCAAAAACC'}
# Window [CCAAAAACCC]: Not seen → seen={...,'CCAAAAACCC'}
# Window [CAAAAACCCC]: Not seen → seen={...,'CAAAAACCCC'}
# Window [AAAAACCCCC]: SEEN! ✅ → repeated={'AAAAACCCCC'}
# Window [AAAACCCCCC]: Not seen → seen={...,'AAAACCCCCC'}
# Window [AAACCCCCC A]: Not seen → continue...
# Window [CCCCCAAAAA]: SEEN! ✅ → repeated={'AAAAACCCCC','CCCCCAAAAA'}
# ...continue...
# Result: ['AAAAACCCCC', 'CCCCCAAAAA']
```


### 🎯 String Matching Problem List

**1️⃣ Permutation in String (LC 567)** - Check if s2 contains permutation of s1 - **Key insight**: Fixed window with frequency matching

**2️⃣ Find All Anagrams in String (LC 438)** - Find all anagram start indices - **Key insight**: Same as above, collect all matches

**3️⃣ Substring with Concatenation of All Words (LC 30)** - Find concat of all words - **Key insight**: Word-level sliding window

**4️⃣ Repeated DNA Sequences (LC 187)** - Find repeated 10-letter sequences - **Key insight**: Fixed window with hash set

**5️⃣ Valid Anagram (LC 242)** - Check if two strings are anagrams - **Key insight**: Simple frequency comparison

**6️⃣ Group Anagrams (LC 49)** - Group strings by anagram - **Key insight**: Hash by sorted string or frequency tuple

***

## 6️⃣ **Comprehensive Comparison Table**

| 🎯 **Approach** | ⏰ **Time Complexity** | 💾 **Space Complexity** | 🛠️ **Best Use Cases** | 📝 **Key Insights** | 🎪 **Template Pattern** |
| :-- | :-- | :-- | :-- | :-- | :-- |
| **Fixed Window** | O(n) | O(1) to O(k) | Known window size, process all k-length subarrays | Window size constant, slide by removing left \& adding right | Initialize window → Slide → Update result each step |
| **Longest Valid Window** | O(n) | O(k) | Find maximum/longest with constraint | Expand first, shrink when invalid, update after valid | Expand right → Shrink while invalid → Update max |
| **Shortest Valid Window** | O(n) | O(k) | Find minimum/shortest satisfying condition | Expand until valid, shrink while valid, update when shrinking | Expand right → Shrink while valid → Update min |
| **String Matching** | O(n) | O(1) to O(26) | Anagram/permutation detection | Fixed window = pattern length, compare frequencies | Build pattern freq → Slide \& match → Return matches |


***

## 7️⃣ **Problem-to-Approach Mapping**

| **Problem Type** | **🥇 Primary** | **🥈 Secondary** | **🥉 Alternative** | **Example Problems** |
| :-- | :-- | :-- | :-- | :-- |
| **Fixed size K** | Fixed Window | - | - | Max Average (LC 643), K Radius Avg (LC 2090) |
| **Longest with constraint** | Longest Valid | Dynamic Window | - | Longest Substring K Distinct (LC 340), Max Ones III (LC 1004) |
| **Shortest satisfying** | Shortest Valid | Dynamic Window | - | Min Window Substring (LC 76), Min Size Sum (LC 209) |
| **Contains all/permutation** | String Matching | Fixed Window | - | Permutation in String (LC 567), All Anagrams (LC 438) |
| **At most K distinct** | Longest Valid | Hash Map + Window | - | K Distinct Chars (LC 340), Fruits Baskets (LC 904) |
| **Without repeating** | Longest Valid | Hash Set + Window | - | Longest Substring No Repeat (LC 3) |
| **With K replacements** | Longest Valid | Count + Window | - | Character Replacement (LC 424), Max Ones II (LC 487) |
| **Sum ≥ target** | Shortest Valid | Prefix Sum | Two Pointers | Min Size Subarray Sum (LC 209) |


***

## 8️⃣ **Performance Characteristics**

| **Data Size (n)** | **Fixed Window** | **Longest Valid** | **Shortest Valid** | **String Matching** |
| :-- | :-- | :-- | :-- | :-- |
| **n ≤ 100** | ✅ Instant | ✅ Instant | ✅ Instant | ✅ Instant |
| **n ≤ 1,000** | ✅ <1ms | ✅ <1ms | ✅ <1ms | ✅ <1ms |
| **n ≤ 10,000** | ✅ <10ms | ✅ <10ms | ✅ <10ms | ✅ <10ms |
| **n ≤ 100,000** | ✅ <100ms | ✅ <100ms | ✅ <100ms | ✅ <100ms |
| **n ≤ 1,000,000** | ✅ ~1s | ✅ ~1s | ✅ ~1s | ✅ ~1s |
| **n > 1,000,000** | ⚠️ May timeout if constant factor high | ⚠️ Check hash operations | ⚠️ Check shrinking logic | ⚠️ Check frequency comparisons |

**🎯 Performance Tips:**

- ✅ Array indexing faster than hash map for small character sets (use array for lowercase)[^1]
- ✅ Avoid repeated hash map lookups - cache values
- ✅ Use `matches` counter instead of comparing entire frequency maps
- ⚠️ String slicing creates new strings (O(k)) - avoid if possible

***

## 9️⃣ **Selection Decision Tree**

```
                    📋 Sliding Window Problem
                              |
                    ┌─────────┴─────────┐
                    │ Window size given? │
                    └─────────┬──────────┘
                              |
            ┌─────────────────┴─────────────────┐
            |                                   |
        YES ✅                               NO ❌
            |                                   |
    ┌───────┴────────┐                ┌────────┴─────────┐
    │ FIXED WINDOW   │                │ Need to find...  │
    │ 📏             │                └────────┬─────────┘
    └────────────────┘                         |
                              ┌────────────────┴────────────────┐
                              |                                 |
                        LONGEST 📏                        SHORTEST 📐
                              |                                 |
                    ┌─────────┴──────────┐          ┌──────────┴──────────┐
                    │ Maximize window    │          │ Minimize window     │
                    │ with constraint    │          │ satisfying condition│
                    └─────────┬──────────┘          └──────────┬──────────┘
                              |                                 |
                    ┌─────────┴──────────┐          ┌──────────┴──────────┐
                    │ At most K distinct?│          │ Contains all target?│
                    └─────────┬──────────┘          └──────────┬──────────┘
                              |                                 |
                        ┌─────┴─────┐                    ┌─────┴──────┐
                        |           |                    |            |
                      YES ✅       NO ❌                YES ✅        NO ❌
                        |           |                    |            |
                  Hash Map +    Count +             Frequency    Check sum/
                  Window      Window              Map Window    product/etc
                        |           |                    |            |
                    LC 340      LC 424              LC 76        LC 209
                    LC 904      LC 1004             LC 438       
```

**🎯 Quick Decision Guide:**

1️⃣ **Is window size k given explicitly?**

- YES → Use **Fixed Window** template
- NO → Continue to step 2

2️⃣ **What are you optimizing?**

- LONGEST/MAXIMUM → Use **Longest Valid Window** template
- SHORTEST/MINIMUM → Use **Shortest Valid Window** template
- EXACT MATCH → Use **String Matching** template

3️⃣ **What's the constraint type?**

- "At most K" → Hash map tracking distinct elements
- "Without repeating" → Hash set detecting duplicates
- "K replacements" → Counter tracking replacements needed
- "Contains all" → Frequency map matching

***

## 🔟 **Common Pitfalls Analysis**

### 🚨 Critical Bug Example: Off-by-One in Fixed Window

#### ❌ WRONG CODE (with bugs):

```python
def maxSumSubarray_WRONG(arr, k):
    """
    🐛 BUG-RIDDEN CODE - DO NOT USE!
    Multiple critical errors that lead to incorrect results
    """
    # Bug 1: No edge case handling
    window_sum = 0
    
    # Bug 2: Wrong range for initial window
    for i in range(k - 1):  # ❌ Missing last element!
        window_sum += arr[i]
    
    max_sum = window_sum
    
    # Bug 3: Wrong sliding logic
    for i in range(k, len(arr)):
        window_sum = window_sum - arr[i - k - 1] + arr[i]  # ❌ Off by one!
        # Bug 4: Updating max BEFORE window is valid
        max_sum = max(max_sum, window_sum)
    
    return max_sum

# 🔍 Let's trace the bugs with arr = [2, 1, 5, 1, 3, 2], k = 3
```


### 📊 Execution Trace - WRONG vs EXPECTED:

| Step | WRONG Code | Expected | Issue |
| :-- | :-- | :-- | :-- |
| **Initialization** | `range(k-1)` = `range(2)` | `range(3)` | ❌ Only sums indices 0,1 → sum=3 |
| Expected | Should sum 2+1+5 = 8 | - | Missing arr[^2]=5 |
| **First slide (i=3)** | `arr[3-3-1]` = `arr[-1]` = 2 | `arr[^0]` = 2 | ❌ Accidental Python wraparound! |
| Calculation | `3 - 2 + 1 = 2` | `8 - 2 + 1 = 7` | Wrong result due to bug \#2 \& \#3 |
| **Second slide (i=4)** | `arr[4-3-1]` = `arr[^0]` = 2 | `arr[^1]` = 1 | ❌ Removing wrong element |
| Calculation | `2 - 2 + 3 = 3` | `7 - 1 + 3 = 9` | Cascading errors |
| **Third slide (i=5)** | `arr[5-3-1]` = `arr[^1]` = 1 | `arr[^2]` = 5 | ❌ Still off by one |
| Calculation | `3 - 1 + 2 = 4` | `9 - 5 + 2 = 6` | Wrong final answer |
| **Final Result** | max_sum = 4 | max_sum = 9 | ❌ Completely wrong! |

### 🔬 Detailed Bug Breakdown:

**🐛 Bug \#1: Missing Edge Case Check**

```python
# ❌ WRONG: No validation
window_sum = 0

# ✅ CORRECT: Check validity
if not arr or len(arr) < k or k <= 0:
    return 0  # or raise exception
```

**🐛 Bug \#2: Incorrect Initial Window Range**

```python
# ❌ WRONG: Missing last element of first window
for i in range(k - 1):  # Only iterates k-1 times!
    window_sum += arr[i]
# For k=3: only sums arr[^0] + arr[^1], missing arr[^2]

# ✅ CORRECT: Include all k elements
for i in range(k):  # Iterates k times
    window_sum += arr[i]
# For k=3: sums arr[^0] + arr[^1] + arr[^2]
```

**🐛 Bug \#3: Off-by-One in Sliding**

```python
# ❌ WRONG: Extra -1 causes off-by-one error
window_sum = window_sum - arr[i - k - 1] + arr[i]
# When i=3, k=3: arr[3-3-1] = arr[-1] (wraps to last element!)

# ✅ CORRECT: Proper index calculation
window_sum = window_sum - arr[i - k] + arr[i]
# When i=3, k=3: arr[3-3] = arr[^0] (correct!)
```

**🐛 Bug \#4: Logic Ordering (Subtle)**

```python
# While this doesn't cause errors in fixed window,
# in dynamic windows, updating result before validation is critical

# ❌ POTENTIALLY WRONG in dynamic window:
window_sum += arr[right]
max_sum = max(max_sum, window_sum)  # Before checking validity!
while invalid(window_sum):
    window_sum -= arr[left]
    left += 1

# ✅ CORRECT: Update only after validation
window_sum += arr[right]
while invalid(window_sum):
    window_sum -= arr[left]
    left += 1
max_sum = max(max_sum, window_sum)  # After window is valid!
```


### ✅ CORRECT CODE Comparison:

```python
def maxSumSubarray_CORRECT(arr, k):
    """
    ✅ CORRECT IMPLEMENTATION
    All bugs fixed with proper validation
    """
    # ✅ Fix Bug 1: Edge case handling
    if not arr or len(arr) < k or k <= 0:
        return 0
    
    # ✅ Fix Bug 2: Correct initial window
    window_sum = 0
    for i in range(k):  # Include all k elements
        window_sum += arr[i]
    
    max_sum = window_sum
    
    # ✅ Fix Bug 3: Correct sliding index
    for i in range(k, len(arr)):
        window_sum = window_sum - arr[i - k] + arr[i]
        max_sum = max(max_sum, window_sum)
    
    return max_sum

# 📊 Trace with arr = [2, 1, 5, 1, 3, 2], k = 3
# Initial: sum(arr[0:3]) = 2+1+5 = 8, max=8
# i=3: sum - arr[^0] + arr[^3] = 8-2+1 = 7, max=8
# i=4: sum - arr[^1] + arr[^4] = 7-1+3 = 9, max=9 ✅
# i=5: sum - arr[^2] + arr[^5] = 9-5+2 = 6, max=9
# Result: 9 ✅ CORRECT!
```


### 🎯 Key Takeaways from Bug Analysis:

| Bug Type | Impact | Prevention |
| :-- | :-- | :-- |
| **Missing edge cases** | Runtime errors, wrong results | Always validate input first |
| **Off-by-one in range** | Incomplete window | Double-check range bounds |
| **Wrong index arithmetic** | Accessing wrong elements | Verify with small example |
| **Update before validation** | Invalid results counted | Update only after confirming validity |


***

## 1️⃣1️⃣ **Interview Success Tips**

### 🎯 Problem Recognition Signals

**🚨 Immediate Sliding Window Indicators:**


| Signal | Example | Confidence |
| :-- | :-- | :-- |
| **"subarray"** or **"substring"** | "longest substring", "maximum subarray" | 🔥 95% |
| **"consecutive"** | "k consecutive elements" | 🔥 98% |
| **"contiguous"** | "contiguous sequence" | 🔥 99% |
| **Size constraint** | "of size k", "length k" | 🔥 90% |
| **"at most"** / **"at least"** | "at most k distinct" | 🔥 85% |
| **"without repeating"** | "without repeating characters" | 🔥 80% |
| **Optimization on sequence** | "maximum sum", "minimum length" | 🔥 70% |

### 🎪 Optimization Strategy Table

| Optimization Goal | Strategy | Example |
| :-- | :-- | :-- |
| **Reduce space** | Use array instead of hash map | O(k) → O(26) for lowercase letters |
| **Reduce comparisons** | Track "matches" counter | Instead of comparing entire hash maps |
| **Avoid string creation** | Use indices instead of slicing | `s[i:j]` creates new string (O(k)) |
| **Early termination** | Return as soon as condition met | Boolean problems |
| **Use optimal data structure** | Array for small charset, hash map for large | Trade-off space vs time |

### 🚨 Common Edge Cases with Code Examples

#### **1️⃣ Empty or Small Input**

```python
# ✅ Always validate input size
def sliding_window(arr, k):
    # Edge case: empty array
    if not arr:
        return 0
    
    # Edge case: k larger than array
    if k > len(arr):
        return 0  # or -1, or raise exception
    
    # Edge case: k = 0 or negative
    if k <= 0:
        return 0
    
    # Main logic here...
```


#### **2️⃣ Single Element Window**

```python
# Edge case: k = 1
# Your algorithm should still work!
# Example: maxSum(arr=[5, 2, 3, 7], k=1) should return 7

def maxSumSubarray(arr, k):
    if len(arr) < k:
        return None
    
    # Works for k=1 too! ✅
    window_sum = sum(arr[:k])
    max_sum = window_sum
    
    for i in range(k, len(arr)):
        window_sum += arr[i] - arr[i - k]
        max_sum = max(max_sum, window_sum)
    
    return max_sum
```


#### **3️⃣ All Elements Same**

```python
# Edge case: arr = [5, 5, 5, 5, 5]
# Make sure you handle non-changing windows correctly

def longestSubstringKDistinct(s, k):
    # When all chars same and k >= 1
    # Result should be len(s)
    if k == 0:
        return 0
    
    char_count = {}
    left = 0
    max_len = 0
    
    for right in range(len(s)):
        char_count[s[right]] = char_count.get(s[right], 0) + 1
        
        while len(char_count) > k:
            char_count[s[left]] -= 1
            if char_count[s[left]] == 0:
                del char_count[s[left]]
            left += 1
        
        max_len = max(max_len, right - left + 1)
    
    return max_len

# s = "aaaaa", k = 1 → returns 5 ✅
```


#### **4️⃣ Window Equals Array Length**

```python
# Edge case: k = len(arr)
# Window doesn't slide, just return the metric for whole array

def maxSumSubarray(arr, k):
    if len(arr) == k:
        return sum(arr)  # ✅ Handle directly
    
    # Rest of sliding logic...
```


#### **5️⃣ Negative Numbers / Special Values**

```python
# Edge case: Array contains negative numbers
# Make sure min/max logic handles negatives correctly

def minSubArrayLen(target, nums):
    # Works with negative numbers if problem allows
    left = 0
    current_sum = 0
    min_len = float('inf')  # ✅ Use infinity, not 0!
    
    for right in range(len(nums)):
        current_sum += nums[right]
        
        while current_sum >= target:  # ✅ Will work with negatives
            min_len = min(min_len, right - left + 1)
            current_sum -= nums[left]
            left += 1
    
    # ✅ Return 0 if no valid window found
    return min_len if min_len != float('inf') else 0
```


### ✅ Debug Checklist

Before submitting your solution, verify:

- [ ] ✅ **Edge case: Empty input** - Does your code handle `arr = []` or `s = ""`?
- [ ] ✅ **Edge case: k = 0** - Returns appropriate value (usually 0 or invalid)?
- [ ] ✅ **Edge case: k > len(arr)** - Returns appropriate value?
- [ ] ✅ **Edge case: k = len(arr)** - Window doesn't slide, returns correct result?
- [ ] ✅ **Initialization: First window** - Correct range? `range(k)` not `range(k-1)`?
- [ ] ✅ **Sliding: Index arithmetic** - `arr[i - k]` not `arr[i - k - 1]`?
- [ ] ✅ **Update timing: Result** - Updated after window is valid?
- [ ] ✅ **Hash map: Cleanup** - Removing keys when count reaches 0?
- [ ] ✅ **Return value: No valid window** - Returning appropriate default (0, -1, `[]`, or `""`)?
- [ ] ✅ **Integer overflow: Large sums** - Using Python's arbitrary precision or checking bounds?
- [ ] ✅ **String operations: Efficiency** - Avoiding unnecessary string creation?
- [ ] ✅ **Boundary: Last window** - Loop condition allows processing last valid window?


### 💡 Interview Communication Tips

**🎤 Verbalize Your Thought Process:**

1. **"This looks like a sliding window problem because..."**
    - Mention: contiguous, optimization, constraint
2. **"I'll use [fixed/dynamic] window because..."**
    - Fixed: "Window size is given as k"
    - Dynamic: "Need to find optimal length based on condition"
3. **"My approach will be..."**
    - Longest: "Expand first, shrink when invalid"
    - Shortest: "Expand until valid, shrink while valid"
4. **"Time complexity will be O(n) because..."**
    - "Each element visited at most twice"
5. **"Space complexity is O(k) for..."**
    - Hash map tracking window state

**🎯 Problem-Solving Template Dialog:**

```
Interviewer: "Find the longest substring with at most k distinct characters."

You: "Okay, let me break this down:

1. 🎯 This is a sliding window problem because we're looking at 
   contiguous substrings and optimizing for length.

2. 📏 I'll use a dynamic window approach since we're finding the 
   LONGEST valid substring - so I'll expand first and shrink when 
   we exceed k distinct characters.

3. 📊 I'll need a hash map to track character frequencies in my window.

4. ⏱️ Time complexity will be O(n) since each character is visited at 
   most twice - once by right pointer, once by left pointer.

5. 💾 Space complexity is O(k) for the hash map storing at most k 
   distinct characters.

Let me code this up..."
```


***

## 1️⃣2️⃣ **ASCII Problem Solving Flow**

### 🎯 Sample Problem: Find Maximum Sum Subarray of Size K

**Problem:** `arr = [^2][^1][^5][^1][^3][^2], k = 3`

```
📋 Input Visualization:
======================
Array: [2️⃣, 1️⃣, 5️⃣, 1️⃣, 3️⃣, 2️⃣]
Index:  0   1   2   3   4   5
Goal: Find max sum of any 3 consecutive elements


🔧 Step 0: Initialize
======================
Window boundaries: left=0, right=2 (size k=3)

[2️⃣, 1️⃣, 5️⃣, 1️⃣, 3️⃣, 2️⃣]
 └──────┘
  Window

window_sum = 2 + 1 + 5 = 8 ✅
max_sum = 8


🔄 Step 1: Slide right to index 3
==================================
[2️⃣, 1️⃣, 5️⃣, 1️⃣, 3️⃣, 2️⃣]
      └──────┘
       Window

Operation: Remove 2️⃣, Add 1️⃣
window_sum = 8 - 2 + 1 = 7
max_sum = max(8, 7) = 8


🔄 Step 2: Slide right to index 4
==================================
[2️⃣, 1️⃣, 5️⃣, 1️⃣, 3️⃣, 2️⃣]
           └──────┘
            Window

Operation: Remove 1️⃣, Add 3️⃣
window_sum = 7 - 1 + 3 = 9 🎯
max_sum = max(8, 9) = 9 ⭐


🔄 Step 3: Slide right to index 5
==================================
[2️⃣, 1️⃣, 5️⃣, 1️⃣, 3️⃣, 2️⃣]
                └──────┘
                 Window

Operation: Remove 5️⃣, Add 2️⃣
window_sum = 9 - 5 + 2 = 6
max_sum = max(9, 6) = 9


🏆 Final Result
===============
Maximum sum: 9
Window: [5️⃣, 1️⃣, 3️⃣] at indices [2, 3, 4]


📊 Complexity Analysis
======================
Time: O(n) - Single pass through array
Space: O(1) - Only variables for sum and max
```


### 🎭 Sample Problem 2: Longest Substring Without Repeating Characters

**Problem:** `s = "abcabcbb"`

```
📋 Input Visualization:
=======================
String: "a b c a b c b b"
Index:   0 1 2 3 4 5 6 7
Goal: Find longest substring with all unique characters


🔧 Step 0: Initialize
======================
left = 0, right = 0
char_set = {}
max_length = 0


🔄 Step 1: right=0, char='a'
============================
"[a] b c a b c b b"
  ↑
Window: {a}
'a' not in set ✅
Add 'a' to set
max_length = 1


🔄 Step 2: right=1, char='b'
============================
"[a b] c a b c b b"
  ↑ ↑
Window: {a, b}
'b' not in set ✅
Add 'b' to set
max_length = 2


🔄 Step 3: right=2, char='c'
============================
"[a b c] a b c b b"
  ↑   ↑
Window: {a, b, c}
'c' not in set ✅
Add 'c' to set
max_length = 3 ⭐


🔄 Step 4: right=3, char='a'
============================
"[a b c a] b c b b"
  ↑     ↑
Window: {a, b, c}
'a' in set! ❌ DUPLICATE!

Shrink window:
  Remove 'a' → set = {b, c}, left=1
  Now 'a' not in set ✅
  
"a [b c a] b c b b"
    ↑   ↑
Window: {b, c, a}
max_length = 3


🔄 Step 5: right=4, char='b'
============================
"a [b c a b] c b b"
    ↑     ↑
Window: {b, c, a}
'b' in set! ❌ DUPLICATE!

Shrink window:
  Remove 'b' → set = {c, a}, left=2
  Now 'b' not in set ✅
  
"a b [c a b] c b b"
      ↑   ↑
Window: {c, a, b}
max_length = 3


🔄 Step 6: right=5, char='c'
============================
"a b [c a b c] b b"
      ↑     ↑
Window: {c, a, b}
'c' in set! ❌ DUPLICATE!

Shrink window:
  Remove 'c' → set = {a, b}, left=3
  Now 'c' not in set ✅
  
"a b c [a b c] b b"
        ↑   ↑
Window: {a, b, c}
max_length = 3


🔄 Step 7: right=6, char='b'
============================
"a b c [a b c b] b"
        ↑     ↑
Window: {a, b, c}
'b' in set! ❌ DUPLICATE!

Shrink window:
  Remove 'a' → set = {b, c}, left=4
  'b' still in set! ❌
  Remove 'b' → set = {c}, left=5
  Now 'b' not in set ✅
  
"a b c a b [c b] b"
            ↑ ↑
Window: {c, b}
max_length = 3


🔄 Step 8: right=7, char='b'
============================
"a b c a b [c b b]"
            ↑   ↑
Window: {c, b}
'b' in set! ❌ DUPLICATE!

Shrink window:
  Remove 'c' → set = {b}, left=6
  'b' still in set! ❌
  Remove 'b' → set = {}, left=7
  Now 'b' not in set ✅
  
"a b c a b c b [b]"
                ↑
Window: {b}
max_length = 3


🏆 Final Result
===============
Longest substring length: 3
Example substrings: "abc", "bca", "cab"


📊 Visual Summary
=================
Original: "a b c a b c b b"
           └─┬─┘         ← "abc" (length 3) ✅
             └─┬─┘       ← "bca" (length 3) ✅
               └─┬─┘     ← "cab" (length 3) ✅
                 └─┬─┘   ← "abc" (length 3) ✅


📊 Complexity Analysis
======================
Time: O(n) - Each char visited at most twice
Space: O(min(n, charset)) - Set stores unique chars
```


***

## 1️⃣3️⃣ **Master Problem Set**

### 🎯 Comprehensive Problem List by Difficulty

| Problem | Difficulty | Key Technique | LC \# |
| :-- | :-- | :-- | :-- |
| **Maximum Average Subarray I** | 🟢 Easy | Fixed window | 643 |
| **Contains Duplicate II** | 🟢 Easy | Fixed window + set | 219 |
| **Max Consecutive Ones** | 🟢 Easy | Dynamic window (k=0 flips) | 485 |
| **Find All Anagrams** | 🟡 Medium | String matching | 438 |
| **Permutation in String** | 🟡 Medium | String matching | 567 |
| **Longest Substring Without Repeating** | 🟡 Medium | Dynamic - longest | 3 |
| **Longest Substring K Distinct** | 🟡 Medium | Dynamic - longest + map | 340 |
| **Max Consecutive Ones III** | 🟡 Medium | Dynamic - longest (k flips) | 1004 |
| **Fruits Into Baskets** | 🟡 Medium | Dynamic - longest (k=2) | 904 |
| **Longest Repeating Character Replacement** | 🟡 Medium | Dynamic - longest + count | 424 |
| **Minimum Size Subarray Sum** | 🟡 Medium | Dynamic - shortest | 209 |
| **Minimum Window Substring** | 🔴 Hard | Dynamic - shortest + freq map | 76 |
| **Sliding Window Maximum** | 🔴 Hard | Fixed + deque | 239 |
| **Minimum Window Subsequence** | 🔴 Hard | Two-pass window | 727 |
| **Substring with Concatenation** | 🔴 Hard | String matching + words | 30 |
| **Smallest Range K Lists** | 🔴 Hard | Dynamic + priority queue | 632 |

### 🎓 Study Path by Experience Level

**🎯 Beginner (Start Here):**

1. Max Average Subarray (LC 643) - Fixed window basics
2. Contains Duplicate II (LC 219) - Fixed window with set
3. Max Consecutive Ones (LC 485) - Simple dynamic window

**🎯 Intermediate (Build Skills):**
4. Longest Substring Without Repeating (LC 3) - Classic dynamic window
5. Permutation in String (LC 567) - String matching
6. Find All Anagrams (LC 438) - String matching variation
7. Max Consecutive Ones III (LC 1004) - Constraint tracking
8. Longest Substring K Distinct (LC 340) - Hash map window

**🎯 Advanced (Master the Pattern):**
9. Longest Repeating Character Replacement (LC 424) - Complex constraint
10. Minimum Size Subarray Sum (LC 209) - Shortest window
11. Minimum Window Substring (LC 76) - Hardest common problem
12. Sliding Window Maximum (LC 239) - Advanced data structure
13. Substring with Concatenation (LC 30) - Word-level window

**🎯 Expert (FAANG Level):**
14. Minimum Window Subsequence (LC 727) - Multi-pass technique
15. Smallest Range K Lists (LC 632) - Multiple input sources
16. Count Subarrays with Score < K (LC 2302) - Binary search hybrid
17. Find Substring with Given Hash Value (LC 2156) - Rolling hash

***

## 1️⃣4️⃣ **Memory Aids**

### 🎯 Memorable Mnemonics

**🪟 WINDOW Framework:**

**W**atch for contiguous sequences 👀
**I**dentify window type (fixed/dynamic) 🎯
**N**avigate with two pointers 👈👉
**D**etermine what to track (sum, count, freq) 📊
**O**ptimize shrink conditions 🔄
**W**in by updating result properly! 🏆

### 📐 Key Formulas \& Conditions

```
🎯 Window Size Formula:
window_size = right - left + 1

🎯 Fixed Window Slide:
window_sum = window_sum - arr[i - k] + arr[i]

🎯 Longest Window Condition:
while (condition_violated):
    shrink_from_left()
update_max_after_shrinking()

🎯 Shortest Window Condition:
while (condition_satisfied):
    update_min_before_shrinking()
    shrink_from_left()

🎯 Frequency Match Check:
if window_count == pattern_count:
    found_match()

🎯 K Distinct Characters:
if len(char_map) > k:
    shrink_until_valid()
```


### 🧠 Pattern-Specific Reminders

**📏 Fixed Window:**

```
Remember: "Initialize → Slide → Update"
🎯 Don't forget to initialize the FIRST window!
🎯 Slide formula: -left +right
🎯 Update result EVERY step
```

**📈 Longest Window:**

```
Remember: "Expand First, Shrink When Bad"
🎯 Add right element FIRST
🎯 WHILE invalid: shrink
🎯 Update max AFTER validation
```

**📉 Shortest Window:**

```
Remember: "Expand Until Good, Shrink While Good"
🎯 Add right element FIRST
🎯 WHILE valid: update min, then shrink
🎯 Return infinity if no valid window
```

**🔤 String Matching:**

```
Remember: "Build Pattern, Match Exactly"
🎯 Window size = len(pattern)
🎯 Use frequency arrays for small charset
🎯 Track "matches" count for optimization
```


### 🎪 Quick Reference Card

```
╔═══════════════════════════════════════════════════╗
║         🪟 SLIDING WINDOW CHEAT SHEET              ║
╠═══════════════════════════════════════════════════╣
║ 📏 FIXED SIZE:                                     ║
║   • Window size = k (given)                       ║
║   • Initialize first k elements                   ║
║   • Slide: -arr[i-k] +arr[i]                     ║
║   • Time: O(n), Space: O(1)                       ║
║                                                   ║
║ 📈 LONGEST VALID:                                  ║
║   • Goal: maximize window size                    ║
║   • Expand right, shrink while invalid           ║
║   • Update max AFTER validation                   ║
║   • Time: O(n), Space: O(k)                       ║
║                                                   ║
║ 📉 SHORTEST VALID:                                 ║
║   • Goal: minimize window size                    ║
║   • Expand right, shrink while valid             ║
║   • Update min BEFORE shrinking                   ║
║   • Time: O(n), Space: O(k)                       ║
║                                                   ║
║ 🔤 STRING MATCHING:                                ║
║   • Window size = len(pattern)                    ║
║   • Compare frequency maps                        ║
║   • Fixed window slide                            ║
║   • Time: O(n), Space: O(charset)                 ║
╚═══════════════════════════════════════════════════╝
```


### 💡 Interview Day Reminders

**Before coding, ask yourself:**

1. ✅ Is window size fixed or variable?
2. ✅ Am I maximizing or minimizing?
3. ✅ What needs to be tracked in window state?
4. ✅ When do I update the result?
5. ✅ What are the edge cases?

**During coding:**

1. ✅ Initialize window properly
2. ✅ Check index arithmetic carefully
3. ✅ Update result at correct time
4. ✅ Clean up hash maps (remove zeros)
5. ✅ Handle edge cases explicitly

**After coding:**

1. ✅ Trace through with small example
2. ✅ Check edge cases
3. ✅ Verify time/space complexity
4. ✅ Test with interviewer's examples

***

## 🎓 Final Words

The **Sliding Window** pattern is one of the most powerful and frequently tested techniques in coding interviews. Master these four variations:

1. 📏 **Fixed Window** - When size is given
2. 📈 **Longest Valid** - When maximizing with constraint
3. 📉 **Shortest Valid** - When minimizing while satisfying condition
4. 🔤 **String Matching** - When checking permutations/anagrams

**🎯 Key to Success:**

- ✅ Recognize the pattern from problem keywords
- ✅ Choose the right template
- ✅ Handle edge cases carefully
- ✅ Communicate your thought process clearly

**💪 Practice Makes Perfect:**
Start with easy problems, build confidence, then tackle harder variations. With consistent practice, you'll instantly recognize sliding window problems and implement solutions efficiently.

**🚀 You've got this!** The sliding window pattern will become your secret weapon for conquering array and string problems. Keep the templates handy, practice regularly, and you'll ace those coding interviews! 💯

***

*"The window slides, the code glides, and success arrives!"* 🪟✨

<div align="center">⁂</div>

[^1]: https://aclanthology.org/2023.emnlp-main.897.pdf

[^2]: https://www.nature.com/articles/s41597-024-04019-z

