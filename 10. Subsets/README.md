# 🔀 Subsets, Combinations & Permutations — Complete FAANG Interview Guide

> 🏆 *Master the most powerful combinatorial pattern in coding interviews — from beginner fundamentals to FAANG-level mastery.*

***

## 1️⃣ Pattern Overview

### 🎯 Core Concept

The **Subsets / Combinations / Permutations** pattern is one of the most frequently tested patterns in FAANG interviews. It covers a family of problems where you must generate **all possible arrangements or selections** from a given set of elements.[^1]

```
📥 INPUT          ⚙️ PROCESS               📤 OUTPUT
─────────         ──────────────────────   ──────────────────────────
Array/String  →   Backtracking DFS Tree →  All valid subsets /
[1, 2, 3]         (Choose / Explore /      combinations /
                   Unchoose)               permutations
```

**Three core sub-types:**

| Type | Definition | Order Matters? | Example |
|------|-----------|---------------|---------|
| **Subsets** | All selections (including empty) | ❌ No | `[1,2,3]` → `[], [^1], [^2], [^3], [1,2], [1,3], [2,3], [1,2,3]` |
| **Combinations** | Selections of fixed size `k` | ❌ No | Choose 2 from `[1,2,3]` → `[1,2], [1,3], [2,3]` |
| **Permutations** | All orderings of elements | ✅ Yes | `[1,2]` → `[1,2], [2,1]` |

### 🧠 When & Why to Use This Pattern

Use this pattern when the problem asks you to:
- Generate **all possible subsets** (power set) of a collection[^2]
- Find all **combinations** that satisfy a condition (e.g., sum to target)[^3]
- Produce all **orderings/arrangements** of a sequence[^3]
- Partition a string or array into valid segments[^4]

### ⏰ Complexity Overview

| Operation | Time | Space |
|-----------|------|-------|
| Subsets | O(n × 2ⁿ) | O(n) recursion depth + O(2ⁿ) output |
| Combinations (n choose k) | O(k × C(n,k)) | O(k) path + O(C(n,k)) output |
| Permutations | O(n × n!) | O(n) path + O(n!) output |

***

## 2️⃣ 🔍 Pattern Recognition & Detection

### ✅ Rules for Identifying This Pattern

**Use Subsets/Combinations/Permutations when you see:**

- 🔑 Keywords: *"all possible"*, *"generate all"*, *"list all"*, *"power set"*, *"enumerate"*
- 🔑 Phrases: *"find all subsets"*, *"all combinations that sum to"*, *"all arrangements"*
- 🔑 Problem structure: Input is array/string → Output is list of lists
- 🔑 Constraints: small `n` (≤ 20 for subsets, ≤ 12 for permutations)

### 🚦 Key Problem Signals

```
✅ USE THIS PATTERN IF:           ❌ AVOID IF:
──────────────────────────────    ──────────────────────────────
"Return all possible..."          "Return the count of..."
Output is List[List[...]]         Output is a single number
n ≤ 20 (exponential is OK)        n is large (> 30)
Need to enumerate solutions       Need only ONE valid solution
```

### 🎨 ASCII Visual — The Decision Tree

```
                    🎯 START: []
                   /      |      \
              Pick 1    Pick 2   Pick 3
              [^1]        [^2]      [^3]
             / \          |
        Pick 2 Pick 3  Pick 3
        [1,2]  [1,3]   [2,3]
          |
        Pick 3
        [1,2,3]

📊 Result for [1,2,3]:
  [] ✅  [^1] ✅  [^2] ✅  [^3] ✅
  [1,2] ✅  [1,3] ✅  [2,3] ✅
  [1,2,3] ✅

🔢 Total = 2^n = 2^3 = 8 subsets
```

### 🔄 Backtracking Core Idea

```
🎭 THREE MAGICAL STEPS:
┌─────────────────────────────────┐
│  1️⃣ CHOOSE   → path.append(x)   │
│  2️⃣ EXPLORE  → backtrack(...)   │
│  3️⃣ UNCHOOSE → path.pop()       │
└─────────────────────────────────┘

Like exploring a maze 🌿:
  ➡️ Go down a path
  🔁 Hit a dead end? Retrace steps
  ➡️ Try another direction
  🏁 Collect all valid paths
```

***

## 3️⃣ 🛠️ Standard Algorithm Template

```python
from typing import List

def backtrack_template(nums: List[int]) -> List[List[int]]:
    result = []  # 🎯 Stores all valid answers

    def backtrack(start: int, path: List[int]):
        # 1️⃣ COLLECT: Record current state as a valid answer
        result.append(path[:])  # ✅ Make a copy — not a reference!

        # 2️⃣ EXPLORE: Try each choice from current position
        for i in range(start, len(nums)):

            # 3️⃣ PRUNE (optional): Skip duplicates or invalid choices
            if i > start and nums[i] == nums[i - 1]:
                continue  # ❌ Skip duplicate at same level

            # 4️⃣ CHOOSE: Add element to current path
            path.append(nums[i])  # 🔄 Make a choice

            # 5️⃣ RECURSE: Explore deeper with updated start
            backtrack(i + 1, path)  # 🚀 Go deeper

            # 6️⃣ UNCHOOSE: Remove element (backtrack)
            path.pop()  # 🔙 Undo the choice

    backtrack(0, [])
    return result
```

**Template Variants at a Glance:**

```python
# 🎯 SUBSETS: Collect at every node
result.append(path[:])       # ← collect ALWAYS

# 🎯 COMBINATIONS: Collect at leaf (when path size = k)
if len(path) == k:
    result.append(path[:])

# 🎯 PERMUTATIONS: Collect at leaf (when path = full length)
if len(path) == len(nums):
    result.append(path[:])
```

***

## 4️⃣ 📋 Common Interview Problem Types

**1️⃣ Subsets (LC 78)** — *Easy/Medium*
Generate all possible subsets of a set with distinct integers.

**Key insight:** BFS iterative OR DFS backtracking; collect path at every node.

```python
from typing import List

class Solution:
    def subsets(self, nums: List[int]) -> List[List[int]]:
        """
        🎯 Goal: Return ALL possible subsets (power set) of distinct integers.
        📥 Input:  nums = [1, 2, 3]
        📤 Output: [[], [1], [2], [3], [1,2], [1,3], [2,3], [1,2,3]]
        """
        result = []

        def backtrack(start: int, path: List[int]):
            # 1️⃣ COLLECT at EVERY node (not just leaves)
            result.append(path[:])  # ✅ snapshot — must copy!

            # 2️⃣ EXPLORE: try each element from 'start' onwards
            for i in range(start, len(nums)):
                path.append(nums[i])      # 🔄 CHOOSE
                backtrack(i + 1, path)    # 🚀 EXPLORE (i+1 = no reuse)
                path.pop()                # 🔙 UNCHOOSE

        backtrack(0, [])
        return result

# ─────────────────────────────────────────
# ⏰ Time:  O(n * 2^n)  — 2^n subsets, each copied in O(n)
# 💾 Space: O(n)        — recursion depth
# ─────────────────────────────────────────
# 🧪 Test:
sol = Solution()
print(sol.subsets([1, 2, 3]))
# [[], [1], [1, 2], [1, 2, 3], [1, 3], [2], [2, 3], [3]]
print(sol.subsets([0]))
# [[], [0]]
```

**2️⃣ Subsets II (LC 90)** — *Medium*[^5]
Same as above but input may contain duplicates.

**Key insight:** Sort first, then skip `nums[i] == nums[i-1]` at the same recursion level.
```python
class Solution:
    def subsetsWithDup(self, nums: List[int]) -> List[List[int]]:
        """
        🎯 Goal: Return all unique subsets from array that MAY contain duplicates.
        📥 Input:  nums = [1, 2, 2]
        📤 Output: [[], [1], [1,2], [1,2,2], [2], [2,2]]

        🔑 Key Trick:
          - Sort first so duplicates are adjacent
          - At the same recursion level, skip nums[i] if it equals nums[i-1]
          - 'i > start' ensures we only skip siblings, NOT deeper branches
        """
        nums.sort()  # 1️⃣ Sort to group duplicates 🔑
        result = []

        def backtrack(start: int, path: List[int]):
            result.append(path[:])  # ✅ collect every node

            for i in range(start, len(nums)):
                # 2️⃣ Skip duplicate at SAME level
                # 'i > start' means: only skip if we already used
                # a sibling with the same value at this level
                if i > start and nums[i] == nums[i - 1]:
                    continue  # ❌ skip duplicate sibling

                path.append(nums[i])      # 🔄 CHOOSE
                backtrack(i + 1, path)    # 🚀 EXPLORE
                path.pop()                # 🔙 UNCHOOSE

        backtrack(0, [])
        return result

# ─────────────────────────────────────────
# ⏰ Time:  O(n * 2^n)
# 💾 Space: O(n)
# ─────────────────────────────────────────
# 🧪 Test:
sol = Solution()
print(sol.subsetsWithDup([1, 2, 2]))
# [[], [1], [1, 2], [1, 2, 2], [2], [2, 2]]
print(sol.subsetsWithDup([0]))
# [[], [0]]
```

**3️⃣ Combination Sum (LC 39)** — *Medium*
Find all combinations that sum to a target; elements can be reused.

**Key insight:** Pass same index `i` (not `i+1`) to allow reuse; stop when sum exceeds target.

```python
class Solution:
    def combinationSum(self, candidates: List[int], target: int) -> List[List[int]]:
        """
        🎯 Goal: Find all unique combinations that SUM to target.
                 Each candidate may be used UNLIMITED times.
        📥 Input:  candidates = [2, 3, 6, 7], target = 7
        📤 Output: [[2, 2, 3], [7]]

        🔑 Key Tricks:
          - Pass 'i' (NOT i+1) to allow reuse of same element
          - Prune when remaining < 0
          - Sorting candidates enables early 'break' pruning
        """
        candidates.sort()  # 1️⃣ Sort for early break optimization
        result = []

        def backtrack(start: int, path: List[int], remaining: int):
            # 2️⃣ Base case: exact match found ✅
            if remaining == 0:
                result.append(path[:])
                return

            for i in range(start, len(candidates)):
                # 3️⃣ Prune: if current candidate > remaining, all further
                #    candidates (sorted) will also exceed → break, not continue
                if candidates[i] > remaining:
                    break  # ❌ pruning optimization

                path.append(candidates[i])           # 🔄 CHOOSE
                backtrack(i, path, remaining - candidates[i])  # 🚀 pass i (allow reuse!)
                path.pop()                           # 🔙 UNCHOOSE

        backtrack(0, [], target)
        return result

# ─────────────────────────────────────────
# ⏰ Time:  O(n ^ (T/M))  where T=target, M=min(candidates)
# 💾 Space: O(T/M)        max recursion depth
# ─────────────────────────────────────────
# 🧪 Test:
sol = Solution()
print(sol.combinationSum([2, 3, 6, 7], 7))
# [[2, 2, 3], [7]]
print(sol.combinationSum([2, 3, 5], 8))
# [[2, 2, 2, 2], [2, 3, 3], [3, 5]]
print(sol.combinationSum([2], 1))
# []  ← no valid combination
```

**4️⃣ Permutations (LC 46)** — *Medium*[^3]
Return all orderings of distinct integers.

**Key insight:** Use `visited[]` boolean array; do NOT pass `start`; iterate from index 0 each time.

```python
class Solution:
    def permute(self, nums: List[int]) -> List[List[int]]:
        """
        🎯 Goal: Return ALL possible orderings (permutations) of distinct integers.
        📥 Input:  nums = [1, 2, 3]
        📤 Output: [[1,2,3],[1,3,2],[2,1,3],[2,3,1],[3,1,2],[3,2,1]]

        🔑 Key Differences from Subsets:
          - NO 'start' index — loop from 0 every time
          - Use visited[] to avoid picking an element twice in same path
          - Collect only at LEAF nodes (when path is full)
        """
        result = []
        visited = [False] * len(nums)  # 🎯 track which elements are in current path

        def backtrack(path: List[int]):
            # 1️⃣ Base case: permutation complete (leaf node)
            if len(path) == len(nums):
                result.append(path[:])  # ✅ full permutation
                return

            # 2️⃣ Try EVERY element at each position (loop from 0!)
            for i in range(len(nums)):
                if visited[i]:
                    continue  # ❌ already in current path

                visited[i] = True           # 🔄 CHOOSE
                path.append(nums[i])
                backtrack(path)             # 🚀 EXPLORE
                path.pop()                  # 🔙 UNCHOOSE
                visited[i] = False

        backtrack([])
        return result

# ─── ALTERNATIVE: Swap-based (in-place, no extra visited array) ───
class SolutionSwap:
    def permute(self, nums: List[int]) -> List[List[int]]:
        result = []

        def backtrack(start: int):
            if start == len(nums):
                result.append(nums[:])  # ✅ snapshot current arrangement
                return
            for i in range(start, len(nums)):
                nums[start], nums[i] = nums[i], nums[start]  # 🔄 swap
                backtrack(start + 1)                          # 🚀 recurse
                nums[start], nums[i] = nums[i], nums[start]  # 🔙 swap back

        backtrack(0)
        return result

# ─────────────────────────────────────────
# ⏰ Time:  O(n * n!)  — n! permutations, each copied in O(n)
# 💾 Space: O(n)       — visited array + recursion depth
# ─────────────────────────────────────────
# 🧪 Test:
sol = Solution()
print(sol.permute([1, 2, 3]))
# [[1,2,3],[1,3,2],[2,1,3],[2,3,1],[3,1,2],[3,2,1]]
print(sol.permute([0, 1]))
# [[0,1],[1,0]]
print(sol.permute([1]))
# [[1]]
```

**5️⃣ Letter Combinations of Phone Number (LC 17)** — *Medium*[^6]
Map digits to letters (phone keypad), return all combinations.
**Key insight:** Each digit maps to 3-4 letters; recurse through digits, not indices.

```python
class Solution:
    def letterCombinations(self, digits: str) -> List[str]:
        """
        🎯 Goal: Return all possible letter combinations a digit string could represent
                 based on phone keypad mapping.
        📥 Input:  digits = "23"
        📤 Output: ["ad","ae","af","bd","be","bf","cd","ce","cf"]

        🔑 Key Tricks:
          - Map each digit to its letters (phone keypad)
          - Recurse through digits (not through letters at same level)
          - Index tracks which digit we're currently processing
        """
        # 1️⃣ Edge case: empty input
        if not digits:
            return []

        # 2️⃣ Phone keypad mapping 📱
        phone_map = {
            "2": "abc", "3": "def", "4": "ghi", "5": "jkl",
            "6": "mno", "7": "pqrs", "8": "tuv", "9": "wxyz"
        }

        result = []

        def backtrack(index: int, path: List[str]):
            # 3️⃣ Base case: processed all digits
            if index == len(digits):
                result.append("".join(path))  # ✅ join list to string
                return

            # 4️⃣ Get all letters for current digit
            current_letters = phone_map[digits[index]]

            for letter in current_letters:
                path.append(letter)           # 🔄 CHOOSE
                backtrack(index + 1, path)    # 🚀 EXPLORE next digit
                path.pop()                    # 🔙 UNCHOOSE

        backtrack(0, [])
        return result

# ─── ALTERNATIVE: BFS Iterative (clean one-liner style) ───
class SolutionBFS:
    def letterCombinations(self, digits: str) -> List[str]:
        if not digits:
            return []
        phone_map = {
            "2": "abc", "3": "def", "4": "ghi", "5": "jkl",
            "6": "mno", "7": "pqrs", "8": "tuv", "9": "wxyz"
        }
        result = [""]
        for digit in digits:
            # 🔄 Cascade: cross-product existing strings with new letters
            result = [prev + ch for prev in result for ch in phone_map[digit]]
        return result

# ─────────────────────────────────────────
# ⏰ Time:  O(4^n * n)  — at most 4 letters/digit, n = len(digits)
# 💾 Space: O(n)        — recursion depth (DFS) or O(4^n) output
# ─────────────────────────────────────────
# 🧪 Test:
sol = Solution()
print(sol.letterCombinations("23"))
# ['ad','ae','af','bd','be','bf','cd','ce','cf']
print(sol.letterCombinations(""))
# []
print(sol.letterCombinations("2"))
# ['a', 'b', 'c']
print(sol.letterCombinations("79"))
# 16 combinations: 'pw','px','py','pz','qw','qx',...
```


**6️⃣ Palindrome Partitioning (LC 131)** — *Medium*[^7]
Partition a string such that every substring is a palindrome.

**Key insight:** At each index, try all substrings starting there; only recurse if palindrome.

```python
class Solution:
    def partition(self, s: str) -> List[List[str]]:
        """
        🎯 Goal: Partition string s so every substring is a palindrome.
                 Return all possible valid partitions.
        📥 Input:  s = "aab"
        📤 Output: [["a","a","b"],["aa","b"]]

        🔑 Key Tricks:
          - At each position, try ALL possible ending indices
          - Only recurse if current substring is a palindrome (pruning!)
          - Optional: precompute palindrome table with DP for O(1) checks
        """
        result = []
        n = len(s)

        # ── APPROACH A: Inline palindrome check (simple) ──────────────
        def is_palindrome(left: int, right: int) -> bool:
            """Check if s[left..right] inclusive is a palindrome."""
            while left < right:
                if s[left] != s[right]:
                    return False
                left += 1
                right -= 1
            return True

        def backtrack(start: int, path: List[str]):
            # 1️⃣ Base case: consumed entire string ✅
            if start == n:
                result.append(path[:])
                return

            # 2️⃣ Try every possible end for current substring
            for end in range(start, n):
                if is_palindrome(start, end):          # 🔍 prune non-palindromes
                    path.append(s[start:end + 1])      # 🔄 CHOOSE
                    backtrack(end + 1, path)            # 🚀 EXPLORE from end+1
                    path.pop()                         # 🔙 UNCHOOSE
                # If not palindrome, simply don't recurse — natural pruning ❌

        backtrack(0, [])
        return result

# ─── OPTIMISED APPROACH B: Precompute palindrome DP table ──────────
class SolutionOptimised:
    def partition(self, s: str) -> List[List[str]]:
        n = len(s)

        # 1️⃣ Precompute dp[i][j] = True if s[i..j] is palindrome  O(n²)
        dp = [[False] * n for _ in range(n)]
        for i in range(n):
            dp[i][i] = True  # single chars are always palindromes ✅
        for length in range(2, n + 1):
            for i in range(n - length + 1):
                j = i + length - 1
                if s[i] == s[j]:
                    dp[i][j] = (length == 2) or dp[i + 1][j - 1]

        result = []

        def backtrack(start: int, path: List[str]):
            if start == n:
                result.append(path[:])
                return
            for end in range(start, n):
                if dp[start][end]:           # 🎯 O(1) palindrome check!
                    path.append(s[start:end + 1])
                    backtrack(end + 1, path)
                    path.pop()

        backtrack(0, [])
        return result

# ─────────────────────────────────────────
# Approach A:
#   ⏰ Time:  O(n * 2^n)  — 2^n partitions, palindrome check O(n)
#   💾 Space: O(n)         — recursion depth
# Approach B (Optimised):
#   ⏰ Time:  O(n * 2^n)  — but palindrome checks are O(1)
#   💾 Space: O(n²)        — DP table
# ─────────────────────────────────────────
# 🧪 Test:
sol = Solution()
print(sol.partition("aab"))
# [['a', 'a', 'b'], ['aa', 'b']]
print(sol.partition("a"))
# [['a']]
print(sol.partition("racecar"))
# Includes ['racecar'] as entire string is palindrome ✅
print(sol.partition("abc"))
# [['a','b','c']]  ← only single chars are palindromes
```

***

## 5️⃣ 🔬 Advanced Techniques

### Technique 1: 🌿 Classic Backtracking (Subsets & Combinations)

**When to use:** Problems asking for all subsets or combinations where order does NOT matter.[^3]

#### 🔬 Detailed Breakdown

The key insight is that each element has exactly two choices: **include** or **exclude**. We use a `start` index to ensure we never pick an element we've already passed, which prevents duplicate combinations.[^8]

```python
# ✅ TECHNIQUE 1: Classic Backtracking for Subsets
# LC 78 — Subsets
class Solution:
    def subsets(self, nums: List[int]) -> List[List[int]]:
        result = []

        def backtrack(start: int, path: List[int]):
            # 1️⃣ Collect current path as valid subset (even empty set)
            result.append(path[:])  # ✅ snapshot of current state

            # 2️⃣ Try adding each remaining element
            for i in range(start, len(nums)):
                path.append(nums[i])       # 🔄 CHOOSE
                backtrack(i + 1, path)     # 🚀 EXPLORE (i+1 ensures no repeat)
                path.pop()                 # 🔙 UNCHOOSE

        backtrack(0, [])
        return result
        # ⏰ Time: O(n * 2^n)  💾 Space: O(n)
```

#### 📊 Visual Walkthrough — `nums = [1, 2, 3]`

```
backtrack(0, [])
├── ✅ collect []
├── i=0: append 1 → backtrack(1, [^1])
│   ├── ✅ collect [^1]
│   ├── i=1: append 2 → backtrack(2, [1,2])
│   │   ├── ✅ collect [1,2]
│   │   ├── i=2: append 3 → backtrack(3, [1,2,3])
│   │   │   └── ✅ collect [1,2,3]
│   │   └── pop → [1,2]
│   ├── pop → [^1]
│   ├── i=2: append 3 → backtrack(3, [1,3])
│   │   └── ✅ collect [1,3]
│   └── pop → [^1]
├── pop → []
├── i=1: append 2 → ... (similar pattern)
└── i=2: append 3 → ... (similar pattern)

🏆 Final: [[], [^1], [1,2], [1,2,3], [1,3], [^2], [2,3], [^3]]
```

#### 💻 Complete Coding Examples

**Example A — Combination Sum (LC 39):**
```python
class Solution:
    def combinationSum(self, candidates: List[int], target: int) -> List[List[int]]:
        result = []

        def backtrack(start: int, path: List[int], remaining: int):
            # 1️⃣ Base case: found valid combination
            if remaining == 0:
                result.append(path[:])  # ✅ exact match
                return
            # 2️⃣ Prune: exceeded target
            if remaining < 0:
                return  # ❌ prune this branch

            for i in range(start, len(candidates)):
                path.append(candidates[i])
                # 3️⃣ Pass i (NOT i+1) to allow reuse of same element 🔄
                backtrack(i, path, remaining - candidates[i])
                path.pop()  # 🔙 backtrack

        backtrack(0, [], target)
        return result
        # ⏰ Time: O(n^(T/M)) where T=target, M=min candidate
        # 💾 Space: O(T/M) recursion depth
```

**Example B — Combinations (LC 77):**
```python
class Solution:
    def combine(self, n: int, k: int) -> List[List[int]]:
        result = []

        def backtrack(start: int, path: List[int]):
            # 1️⃣ Collect only when path reaches size k
            if len(path) == k:
                result.append(path[:])  # ✅ valid combination of size k
                return

            # 2️⃣ Pruning: need (k - len(path)) more elements
            #    can only pick from start to n - (k - len(path)) + 1
            need = k - len(path)
            for i in range(start, n - need + 2):  # 🎯 optimized bound
                path.append(i)
                backtrack(i + 1, path)
                path.pop()

        backtrack(1, [])
        return result
        # ⏰ Time: O(k * C(n,k))  💾 Space: O(k)
```

**Example C — Combination Sum II (LC 40):**
```python
class Solution:
    def combinationSum2(self, candidates: List[int], target: int) -> List[List[int]]:
        candidates.sort()  # 1️⃣ Sort to group duplicates together 🔑
        result = []

        def backtrack(start: int, path: List[int], remaining: int):
            if remaining == 0:
                result.append(path[:])  # ✅ found valid combo
                return

            for i in range(start, len(candidates)):
                if candidates[i] > remaining:
                    break  # ❌ prune: sorted, so all future > remaining

                # 2️⃣ Skip duplicates at same level (not same branch!)
                if i > start and candidates[i] == candidates[i - 1]:
                    continue  # ❌ skip duplicate

                path.append(candidates[i])
                backtrack(i + 1, path, remaining - candidates[i])  # 🚀 i+1: no reuse
                path.pop()

        backtrack(0, [], target)
        return result
        # ⏰ Time: O(2^n)  💾 Space: O(n)
```

#### 🎯 Problem Examples — Technique 1
1️⃣ **Subsets (LC 78)** — Generate all subsets — Key insight: Collect at every node
2️⃣ **Subsets II (LC 90)** — Subsets with duplicates — Key insight: Sort + skip `nums[i]==nums[i-1]`[^5]
3️⃣ **Combination Sum (LC 39)** — Target sum, reuse OK — Key insight: Pass `i`, not `i+1`
4️⃣ **Combination Sum II (LC 40)** — Target sum, no reuse — Key insight: Sort + prune duplicates
5️⃣ **Combinations (LC 77)** — All k-size combos — Key insight: Optimized loop bound

***

### Technique 2: 🔀 Permutations Backtracking

**When to use:** Order MATTERS; you need every possible arrangement.[^3]

#### 🔬 Detailed Breakdown

Unlike combinations, permutations require you to restart from index 0 at every level and use a `visited` array (or swap technique) to track which elements are already in the current path.[^9]

```python
# ✅ TECHNIQUE 2A: Permutations with visited array
# LC 46 — Permutations
class Solution:
    def permute(self, nums: List[int]) -> List[List[int]]:
        result = []
        visited = [False] * len(nums)  # 🎯 track which elements are used

        def backtrack(path: List[int]):
            # 1️⃣ Base case: permutation is complete
            if len(path) == len(nums):
                result.append(path[:])  # ✅ full permutation found
                return

            # 2️⃣ Try all elements (start from 0 every time!)
            for i in range(len(nums)):
                if visited[i]:
                    continue  # ❌ already in path, skip

                visited[i] = True          # 🔄 CHOOSE
                path.append(nums[i])
                backtrack(path)            # 🚀 EXPLORE
                path.pop()                 # 🔙 UNCHOOSE
                visited[i] = False

        backtrack([])
        return result
        # ⏰ Time: O(n * n!)  💾 Space: O(n)
```

```python
# ✅ TECHNIQUE 2B: Permutations II — with DUPLICATES
# LC 47 — Permutations II
class Solution:
    def permuteUnique(self, nums: List[int]) -> List[List[int]]:
        nums.sort()  # 1️⃣ Sort to detect duplicates 🔑
        result = []
        visited = [False] * len(nums)

        def backtrack(path: List[int]):
            if len(path) == len(nums):
                result.append(path[:])  # ✅ complete permutation
                return

            for i in range(len(nums)):
                if visited[i]:
                    continue

                # 2️⃣ KEY: Skip if same value as previous AND previous unused
                # This ensures we only use duplicates in left-to-right order
                if i > 0 and nums[i] == nums[i-1] and not visited[i-1]:
                    continue  # ❌ skip duplicate at same level

                visited[i] = True
                path.append(nums[i])
                backtrack(path)
                path.pop()
                visited[i] = False

        backtrack([])
        return result
        # ⏰ Time: O(n * n!)  💾 Space: O(n)
```

#### 📊 Visual Walkthrough — Permutations of `[1, 2, 3]`

```
Level 0 (pick 1st element):
  Choose 1️⃣: [1, _, _]   Choose 2️⃣: [2, _, _]   Choose 3️⃣: [3, _, _]
         ↓                        ↓                       ↓
Level 1 (pick 2nd):
  [1,2,_] [1,3,_]          [2,1,_] [2,3,_]          [3,1,_] [3,2,_]
      ↓                        ↓                          ↓
Level 2 (pick 3rd):
[1,2,3]✅ [1,3,2]✅      [2,1,3]✅ [2,3,1]✅      [3,1,2]✅ [3,2,1]✅

🔢 Total = n! = 3! = 6 permutations
🔑 Key difference from subsets: NO start index, use visited[] instead
```

#### 🎯 Problem Examples — Technique 2
1️⃣ **Permutations (LC 46)** — All orderings, distinct — Key insight: Use `visited[]`, loop from 0
2️⃣ **Permutations II (LC 47)** — With duplicates — Key insight: Sort + `nums[i]==nums[i-1] and not visited[i-1]`
3️⃣ **Next Permutation (LC 31)** — One step forward — Key insight: Find rightmost descending suffix
4️⃣ **Permutation Sequence (LC 60)** — k-th permutation — Key insight: Math-based, avoid generating all

***

### Technique 3: 🌲 BFS Iterative (Cascading) Approach

**When to use:** When you want to avoid recursion stack overhead for small inputs; ideal for pure subset generation.[^10][^2]

#### 🔬 Detailed Breakdown

Start with `[[]]`, and for each new number, **take all existing subsets** and create new ones by appending the current number.[^2]

```python
# ✅ TECHNIQUE 3: BFS Iterative / Cascading Subsets
# LC 78 — Subsets (iterative approach)
class Solution:
    def subsets(self, nums: List[int]) -> List[List[int]]:
        # 1️⃣ Start with the empty subset
        result = [[]]  # 🎯 power set begins with empty set

        for num in nums:
            # 2️⃣ Snapshot current length (don't use new subsets in same pass)
            current_len = len(result)

            # 3️⃣ For each existing subset, create a new one with num appended
            for i in range(current_len):
                result.append(result[i] + [num])  # 🔄 cascade new subsets

        return result
        # ⏰ Time: O(n * 2^n)  💾 Space: O(n * 2^n)
```

#### 📊 Visual Cascading Process

```
nums = [1, 2, 3]

Start:        [[]]
                 ↓
After num=1:  [[],  [^1]]
                       ↓
After num=2:  [[], [^1], [^2], [1,2]]
                                 ↓
After num=3:  [[], [^1], [^2], [1,2], [^3], [1,3], [2,3], [1,2,3]]

📊 Each step DOUBLES the number of subsets!
   1 → 2 → 4 → 8 (= 2^3)
```

#### 💻 BFS Approach for Letter Combinations (LC 17)

```python
class Solution:
    def letterCombinations(self, digits: str) -> List[str]:
        if not digits:
            return []  # 1️⃣ Edge case: empty input

        phone_map = {  # 2️⃣ Phone keypad mapping 📱
            "2": "abc", "3": "def", "4": "ghi", "5": "jkl",
            "6": "mno", "7": "pqrs", "8": "tuv", "9": "wxyz"
        }

        result = [""]  # 3️⃣ Start with empty string (like [[]] for subsets)

        for digit in digits:
            letters = phone_map[digit]
            # 4️⃣ Cascade: combine all existing strings with each new letter
            result = [prev + letter for prev in result for letter in letters]

        return result
        # ⏰ Time: O(n * 4^n)  💾 Space: O(4^n)
```

#### 🎯 Problem Examples — Technique 3
1️⃣ **Subsets (LC 78)** — BFS cascading — Key insight: Double result set for each new element[^10]
2️⃣ **Letter Combinations (LC 17)** — BFS product — Key insight: Cross-product with new digit's letters[^6]
3️⃣ **Gray Code (LC 89)** — Single bit change — Key insight: Mirror and prepend bits iteratively

***

### Technique 4: ✂️ Constraint-Based Pruning (Advanced Backtracking)

**When to use:** Problems with additional constraints that allow early termination (sum target, validity checks, palindrome checks).[^4]

```python
# ✅ TECHNIQUE 4: Palindrome Partitioning (LC 131)
class Solution:
    def partition(self, s: str) -> List[List[str]]:
        result = []
        n = len(s)

        def is_palindrome(left: int, right: int) -> bool:
            # 🎯 Check if s[left:right+1] is palindrome
            while left < right:
                if s[left] != s[right]:
                    return False  # ❌ not a palindrome
                left += 1
                right -= 1
            return True  # ✅ confirmed palindrome

        def backtrack(start: int, path: List[str]):
            # 1️⃣ Base case: used all characters
            if start == n:
                result.append(path[:])  # ✅ valid full partition
                return

            # 2️⃣ Try every possible ending for current substring
            for end in range(start, n):
                if is_palindrome(start, end):  # 🔍 only explore palindromes
                    path.append(s[start:end+1])       # 🔄 CHOOSE
                    backtrack(end + 1, path)           # 🚀 EXPLORE
                    path.pop()                         # 🔙 UNCHOOSE
                # ❌ If not palindrome, this branch is pruned automatically

        backtrack(0, [])
        return result
        # ⏰ Time: O(n * 2^n)  💾 Space: O(n)
```

```python
# ✅ N-Queens (LC 51) — Advanced constraint backtracking
class Solution:
    def solveNQueens(self, n: int) -> List[List[str]]:
        result = []
        cols = set()       # 🎯 occupied columns
        diag1 = set()      # 🎯 occupied \ diagonals (row - col)
        diag2 = set()      # 🎯 occupied / diagonals (row + col)
        board = []

        def backtrack(row: int):
            if row == n:
                # 1️⃣ Base case: all n queens placed ✅
                result.append(["".join(r) for r in board])
                return

            for col in range(n):
                # 2️⃣ Check all three threat vectors ❌
                if col in cols or (row - col) in diag1 or (row + col) in diag2:
                    continue  # ❌ pruned — queen would be attacked

                # 3️⃣ Place queen 🔄
                cols.add(col)
                diag1.add(row - col)
                diag2.add(row + col)
                board.append(["." if c != col else "Q" for c in range(n)])

                backtrack(row + 1)  # 🚀 next row

                # 4️⃣ Remove queen 🔙
                cols.remove(col)
                diag1.remove(row - col)
                diag2.remove(row + col)
                board.pop()

        backtrack(0)
        return result
        # ⏰ Time: O(n!)  💾 Space: O(n²)
```

#### 🎯 Problem Examples — Technique 4
1️⃣ **Palindrome Partitioning (LC 131)** — Partition into palindromes — Key insight: Prune non-palindrome branches[^4]
2️⃣ **N-Queens (LC 51)** — Place queens safely — Key insight: Track columns and both diagonals[^11]
3️⃣ **Word Search (LC 79)** — Find word in grid — Key insight: DFS with in-place marking[^4]
4️⃣ **Sudoku Solver (LC 37)** — Fill Sudoku board — Key insight: Row/col/box constraint sets

***

## 6️⃣ 📊 Comprehensive Technique Comparison

| 🎯 Approach | ⏰ Time | 💾 Space | 🛠️ Best Use Cases | 📝 Key Insights | 🎪 Template Pattern |
|------------|---------|----------|-------------------|-----------------|---------------------|
| **Classic DFS Backtracking** | O(n × 2ⁿ) | O(n) | Subsets, combinations | Collect at every node; `start` index prevents reuse | `backtrack(start, path)` |
| **Permutation Backtracking** | O(n × n!) | O(n) | Ordering problems | No `start`; `visited[]` array; loop from 0 | `backtrack(path, visited)` |
| **BFS Cascading** | O(n × 2ⁿ) | O(n × 2ⁿ) | Subsets, letter combos | Iterative; avoid recursion stack | `for x in nums: double result` |
| **Constraint Pruning** | Varies | O(n) | N-Queens, Sudoku, Palindrome | Prune invalid branches early | `if valid: recurse` |
| **Duplicate Handling** | O(n × 2ⁿ) | O(n) | Subsets II, Permutations II | Sort + skip same sibling[^5] | `if i>start and nums[i]==nums[i-1]: skip` |
| **With Reuse** | O(n^(T/M)) | O(T/M) | Combination Sum | Use same index `i` instead of `i+1` | `backtrack(i, path, rem)` |

***

## 7️⃣ 🗺️ Problem-to-Approach Mapping

| Problem Type | 🥇 Primary | 🥈 Secondary | 🥉 Alternative | Example Problems |
|-------------|-----------|-------------|---------------|-----------------|
| All subsets, distinct | Classic DFS | BFS Cascade | Bit manipulation | LC 78 |
| All subsets, duplicates | Classic DFS + sort+skip | — | — | LC 90[^5] |
| Fixed-size combinations | Classic DFS | BFS Cascade | — | LC 77 |
| Combinations summing to target | Constraint DFS | — | — | LC 39, LC 40 |
| All permutations, distinct | Permutation DFS | Swap method | — | LC 46 |
| Permutations with duplicates | Permutation DFS + sort | — | — | LC 47 |
| String partitioning | Constraint DFS | — | DP + backtrack | LC 131 |
| Grid/board constraint | Constraint DFS | BFS | — | LC 51, LC 79, LC 37 |
| Letter mapping combinations | BFS Cascade | DFS | — | LC 17[^6] |

***

## 8️⃣ ⚡ Performance Characteristics

| Input Size (n) | Classic DFS | Permutation DFS | BFS Cascade | Constraint Pruning |
|---------------|------------|-----------------|-------------|-------------------|
| n ≤ 10 | ✅ Excellent | ✅ Excellent | ✅ Excellent | ✅ Excellent |
| n ≤ 15 | ✅ Fast | ⚠️ Slow (n!=1.3T) | ✅ Fast | ✅ Good |
| n ≤ 20 | ⚠️ ~1M ops | ❌ Too slow | ⚠️ Memory heavy | ✅ Usually OK |
| n > 20 | ❌ TLE risk | ❌ TLE | ❌ MLE | ⚠️ Depends on pruning |
| Duplicates | ✅ with sort+skip | ✅ with sort+skip | ⚠️ Need dedup | ✅ with sort |
| With reuse | ✅ pass `i` | N/A | ⚠️ Complex | ✅ |

***

## 9️⃣ 🌳 Selection Decision Tree

```
📋 Problem Analysis:
│
├─ 🔍 Does order matter? (e.g., [1,2] ≠ [2,1])
│   └─ ✅ YES → Use PERMUTATION technique
│           ├─ Has duplicates? → Sort + visited[i-1] check
│           └─ No duplicates? → Simple visited[] array
│
├─ 🔍 Are you generating selections (order irrelevant)?
│   └─ ✅ YES → Use COMBINATION/SUBSET technique
│           ├─ All sizes? → Collect at every node (Subsets)
│           ├─ Fixed size k? → Collect when len(path)==k
│           └─ Sum to target? → Constraint pruning + collect at 0
│
├─ 🔍 Has duplicates in input?
│   └─ ✅ YES → SORT first, then:
│           ├─ Subsets → skip nums[i]==nums[i-1] at same level
│           └─ Permutations → skip if nums[i]==nums[i-1] and not visited[i-1]
│
├─ 🔍 Can elements be reused?
│   └─ ✅ YES (Combination Sum) → Pass i instead of i+1
│   └─ ❌ NO → Pass i+1 to move forward
│
├─ 🔍 Is there a constraint to validate?
│   └─ ✅ YES → Prune invalid branches immediately
│           ├─ Sum exceeds target? → break (if sorted)
│           ├─ Not palindrome? → skip
│           └─ Queen attacks? → skip column/diagonal
│
└─ 🔍 Prefer iterative (no recursion)?
    └─ ✅ YES → BFS Cascading approach
```

***

## 🔟 ⚠️ Common Pitfalls Analysis

### ❌ WRONG Code — The Reference Bug

```python
# 🐛 BUG: Appending path reference instead of a copy!
def subsets_WRONG(nums):
    result = []

    def backtrack(start, path):
        result.append(path)    # ❌ BUG: appends REFERENCE to path
        for i in range(start, len(nums)):
            path.append(nums[i])
            backtrack(i + 1, path)
            path.pop()

    backtrack(0, [])
    return result
```

### 🔍 Bug Breakdown

| # | Bug | Why It's Wrong | Fix |
|---|-----|---------------|-----|
| 🐛 1 | `result.append(path)` | Appends a **reference** — when `path` mutates, all collected entries mutate too | Use `result.append(path[:])` or `result.append(list(path))` |
| 🐛 2 | Missing `nums.sort()` for duplicate problems | Duplicates must be adjacent to be skippable | Add `nums.sort()` before calling backtrack |
| 🐛 3 | Skipping wrong condition: `if i > 0` instead of `if i > start` | `i > 0` skips the first occurrence everywhere, not just at same level | Use `if i > start and nums[i] == nums[i-1]` |
| 🐛 4 | In permutations: using `start` index instead of `visited[]` | Prevents revisiting elements, but `start` doesn't capture used vs. unused properly | Use `visited[]` boolean array for permutations |

### 📊 Bug Execution Trace — Reference Issue

| Step | Action | Buggy `result` | Correct `result` |
|------|--------|---------------|-----------------|
| backtrack(0,[]) | collect `[]` | `[[]]` | `[[]]` ✅ |
| backtrack(1,[^2]) | collect `[^1]` | `[[^1],[^1]]` ← alias! | `[[], [^1]]` ✅ |
| backtrack(2,[^2][^12]) | collect `[1,2]` | `[[1,2],[1,2],[1,2]]` ← all same! | `[[], [^1], [1,2]]` ✅ |
| After pop to `[]` | path mutates | all entries now `[]`! | entries unchanged ✅ |

### ✅ Correct Solutions Comparison

```python
# ✅ FIX 1: Snapshot with slice
result.append(path[:])

# ✅ FIX 2: Snapshot with list constructor
result.append(list(path))

# ✅ FIX 3: Immutable path (creates new list each time — less efficient)
backtrack(i + 1, path + [nums[i]])  # no need to pop!
```

***

## 1️⃣1️⃣ 🎓 Interview Success Tips

### 🔍 Problem Recognition Signals

- Output type is `List[List[...]]` → almost certainly backtracking[^8]
- Keywords: *"all possible"*, *"every combination"*, *"return all"*
- n ≤ 20 in constraints → exponential is acceptable
- Problem says "without duplicates" in output → sort + skip technique needed

### 📊 Optimization Strategies

| Optimization | When to Apply | Impact |
|-------------|---------------|--------|
| Sort input first | Any problem with duplicates | Enables O(1) duplicate skip |
| Early termination `break` | Sorted input + sum > target | Cuts many branches |
| Prune by remaining count | Combinations with size k | `n - i + 1 >= k - len(path)` |
| Memoize `is_palindrome` | Palindrome partitioning | O(n²) precomputation |
| Bit manipulation subsets | Pure subset generation | O(2ⁿ) clean alternative |

### 🧪 Common Edge Cases with Code

```python
# 🔍 Edge Case 1: Empty input
nums = []
# Result should be [[]] for subsets, [] for permutations

# 🔍 Edge Case 2: Single element
nums = [^1]
# Subsets: [[], [^1]]
# Permutations: [[^1]]

# 🔍 Edge Case 3: All duplicates
nums = [2, 2, 2]
# Subsets: [[], [^2], [2,2], [2,2,2]]
# MUST sort first!

# 🔍 Edge Case 4: Negative numbers (Combination Sum)
# If negatives allowed, you can't prune by "sum > target"
# Must add explicit depth/size limit

# 🔍 Edge Case 5: Target = 0
if target == 0:
    return [[]]  # empty combination always valid
```

### ✅ Debug Checklist

- ✅ Are you appending `path[:]` and NOT `path`?
- ✅ For duplicates: Did you sort the input?
- ✅ Is your duplicate-skip condition `i > start` (not `i > 0`)?
- ✅ For permutations: Are you looping from `0` (not `start`)?
- ✅ For reuse allowed: Are you passing `i` (not `i+1`)?
- ✅ For no-reuse: Are you passing `i+1`?
- ✅ Is your base case correct (when to collect)?
- ✅ Are you restoring state after recursion (pop / visited=False)?

***

## 1️⃣2️⃣ 🎬 ASCII Problem Solving Flow

**Sample Problem: Combination Sum II (LC 40) — `candidates=[10,1,2,7,6,1,5], target=8`**

```
📥 INPUT: [10,1,2,7,6,1,5], target=8

1️⃣ SORT: [1, 1, 2, 5, 6, 7, 10]
   🔑 Duplicates now adjacent!

2️⃣ DRAW DECISION TREE (partial):

backtrack(0, [], 8)  ← remaining=8
├── i=0: pick 1️⃣ → [^1], rem=7
│   ├── i=1: pick 1️⃣ → [1,1], rem=6
│   │   ├── i=2: pick 2 → [1,1,2], rem=4
│   │   │   ├── i=3: pick 5 → [1,1,2,5]? rem=-1 ❌ break
│   │   ├── i=3: pick 5 → [1,1,5], rem=1
│   │   │   ├── i=4: pick 6 → rem=-5 ❌ break
│   │   ├── i=4: pick 6 → [1,1,6] rem=0 ✅ COLLECT!
│   ├── i=2: pick 2 → [1,2], rem=5
│   │   ├── i=3: pick 5 → [1,2,5] rem=0 ✅ COLLECT!
│   │   ├── i=4: pick 6 → rem=-1 ❌ break
│   ├── i=3: pick 5 → [1,5], rem=2
│   │   ...
│   ├── i=4: pick 6 → [1,6], rem=1 → no further valid
│   ├── i=5: pick 7 → [1,7] rem=0 ✅ COLLECT!
├── i=1: SKIP (1 == prev 1, i > start=0) ❌ duplicate
├── i=2: pick 2 → [^2], rem=6
│   ├── i=4: pick 6 → [2,6] rem=0 ✅ COLLECT!
...

3️⃣ RESULT:
   ✅ [1,1,6]
   ✅ [1,2,5]
   ✅ [1,7]
   ✅ [2,6]

📊 VISUAL SUMMARY:
  Candidates: [1️⃣, 1️⃣, 2️⃣, 5️⃣, 6️⃣, 7️⃣, 🔟]
  Target: 8
  Valid: {1+1+6} {1+2+5} {1+7} {2+6} = 4 combinations ✅
```

***

## 1️⃣3️⃣ 📚 Master Problem Set

| Problem | Difficulty | Key Technique |
|---------|-----------|---------------|
| Subsets (LC 78) | 🟡 Medium | Classic DFS / BFS Cascade[^2] |
| Subsets II (LC 90) | 🟡 Medium | Sort + duplicate skip[^5] |
| Permutations (LC 46) | 🟡 Medium | `visited[]` array, loop from 0[^3] |
| Permutations II (LC 47) | 🟡 Medium | Sort + `not visited[i-1]` guard |
| Combination Sum (LC 39) | 🟡 Medium | Pass `i` for reuse, prune > target |
| Combination Sum II (LC 40) | 🟡 Medium | Sort + skip + `i+1` no reuse |
| Combination Sum III (LC 216) | 🟡 Medium | Fixed k items summing to n |
| Combinations (LC 77) | 🟡 Medium | Fixed size, optimized loop bound |
| Letter Combinations (LC 17) | 🟡 Medium | BFS cascade / DFS phone map[^6] |
| Palindrome Partitioning (LC 131) | 🟡 Medium | Constraint DFS, prune non-palindromes[^4] |
| Generate Parentheses (LC 22) | 🟡 Medium | Constraint DFS, open/close counts |
| Word Search (LC 79) | 🟡 Medium | Grid DFS, in-place marking[^4] |
| N-Queens (LC 51) | 🔴 Hard | Constraint DFS, col+diag sets[^11] |
| Sudoku Solver (LC 37) | 🔴 Hard | Constraint DFS, row/col/box sets |
| Permutation Sequence (LC 60) | 🔴 Hard | Mathematical, avoid full generation |
| Expression Add Operators (LC 282) | 🔴 Hard | DFS + math expression building |
| Beautiful Arrangement (LC 526) | 🟡 Medium | Permutation + divisibility constraint |

***

## 1️⃣4️⃣ 🧠 Memory Aids

### 🎯 The Master Mnemonic: **"CEU — Choose, Explore, Unchoose"**

```
🔄 Every backtracking problem:
  C → Choose:   path.append(x)
  E → Explore:  backtrack(...)
  U → Unchoose: path.pop()

Never forget the U! It's what makes backtracking work.
```

### 🔑 Key Formulas

```
📐 COUNTING FORMULAS:
  Subsets of n elements:          2ⁿ
  Permutations of n elements:     n!
  Combinations (n choose k):      n! / (k! × (n-k)!)
  Combinations with repetition:   (n+k-1)! / (k! × (n-1)!)

🎯 COMPLEXITY RULE OF THUMB:
  Subsets  → 2ⁿ states → O(n × 2ⁿ) with copy
  Combos   → C(n,k) states → O(k × C(n,k))
  Perms    → n! states → O(n × n!)
```

### 📌 The 5 Killer Questions to Ask First

```
Before coding ANY backtracking problem, ask:
1️⃣ Does ORDER matter? → Yes=Permutation, No=Combination/Subset
2️⃣ Are there DUPLICATES in input? → Yes=Sort+skip
3️⃣ Can elements be REUSED? → Yes=pass i, No=pass i+1
4️⃣ Is there a SIZE constraint? → Yes=collect when len=k
5️⃣ Is there a VALUE constraint? → Yes=prune when exceeded
```

### 🏆 The "SDPRC" Cheatsheet

```
S — Sort input (always do this first if duplicates possible)
D — Duplicate skip: if i > start and nums[i] == nums[i-1]: continue
P — Path copy: result.append(path[:]) NEVER result.append(path)
R — Reuse control: pass i for reuse, i+1 for no reuse
C — Collect condition: always / when len=k / when remaining=0
```

***

> 🚀 **You've got this!** The Subsets / Combinations / Permutations pattern is one of the most beautiful in all of computer science — once you internalize the **Choose → Explore → Unchoose** rhythm and the five killer questions above, you'll confidently tackle any backtracking problem FAANG throws at you. The secret is not memorizing solutions — it's building the intuition to *see* the decision tree before you write a single line of code. Happy coding! 🎉

---

## References

1. [Top LeetCode Patterns for FAANG Coding Interviews](https://www.reddit.com/r/leetcode/comments/wb0z1v/top_leetcode_patterns_for_faang_coding_interviews/) - Top LeetCode Patterns for FAANG Coding Interviews

2. [Pattern 10: Subsets - GitHub](https://github.com/Chanda-Abdul/Several-Coding-Patterns-for-Solving-Data-Structures-and-Algorithms-Problems-during-Interviews/blob/main/%E2%9C%85%20%20Pattern%2010:%20Subsets.md) - A huge number of coding interview problems involve dealing with Permutations and Combinations of a g...

3. [Backtracking for Coding Interviews: Combination vs Permutation ...](https://dev.to/devcorner/backtracking-for-coding-interviews-combination-vs-permutation-with-top-problems-4bn7) - Many problems on platforms like LeetCode revolve around generating combinations, permutations, subse...

4. [Advanced Recursion Problems with Function Calls Inside a Loop ...](https://dev.to/devcorner/advanced-recursion-problems-with-function-calls-inside-a-loop-part-2-201h) - Recursive function calls inside loops appear in backtracking problems like Sudoku, N-Queens, and Pal...

5. [LeetCode 90: Subsets II Solution with Backtracking and Duplicate ...](https://www.linkedin.com/posts/shreya-rana-292367324_leetcode-dsa-backtracking-activity-7404922125511471104-PVJZ) - 📌 Solved LeetCode 90: Subsets II Problem Summary: Given an array where elements may appear more than...

6. [17. Letter Combinations of a Phone Number - Leetcode Solution](https://algomap.io/problems/letter-combinations-of-a-phone-number) - The "Letter Combinations of a Phone Number" problem involves generating all possible strings that ca...

7. [How to master backtracking for interviews - LinkedIn](https://www.linkedin.com/posts/shivam-shrivastava-ab6404179_%F0%9D%97%95%F0%9D%97%AE%F0%9D%97%B0%F0%9D%97%B8%F0%9D%98%81%F0%9D%97%BF%F0%9D%97%AE%F0%9D%97%B0%F0%9D%97%B8%F0%9D%97%B6%F0%9D%97%BB%F0%9D%97%B4-%F0%9D%97%A5%F0%9D%97%B2%F0%9D%97%B0%F0%9D%98%82%F0%9D%97%BF%F0%9D%98%80%F0%9D%97%B6%F0%9D%97%BC%F0%9D%97%BB-activity-7343125738847444995-jAqv) - Essential Problems to Master N-Queens ... This pattern is a gateway to advanced binary search proble...

8. [Mastering Permutations & Combinations with Backtracking](https://medium.com/@Ming1994/mastering-permutations-combinations-with-backtracking-5c66a9b3ea88) - When solving backtracking problems, it’s essential to understand the difference between permutations...

9. [Permutation Algorithm via Backtracking](https://medium.com/@guguru/permutation-algorithm-via-backtracking-39fc1bf07a33) - Overview

10. [Permutations](https://dsa.paulonteri.com/Data%20Structures%20and%20Algorithms%2016913c6fbd244de481b6b1705cbfa6be/_Patterns%20for%20Coding%20Questions%20e3f5361611c147ebb2fb3eff37a743fd/Subsets,%20Permutations%20&%20Combinations%204ac34f48d941479dbcc27b16ae62edea.html)

11. [51. N-Queens - In-Depth Explanation - AlgoMonster](https://algo.monster/liteproblems/51) - Backtracking is perfect here because: We place queens one by one; If a placement leads to a conflict...

12. [Deal with subset, permutation, combination problems using ...](https://wangyy395.medium.com/deal-with-subset-permutation-combination-problems-using-backtracking-algorithm-d50dc8f60f92) - It’s often asked during a technical interview: write a function to get the subsets/combinations/perm...

