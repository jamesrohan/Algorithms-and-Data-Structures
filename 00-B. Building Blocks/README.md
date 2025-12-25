# 🐍 Python Data Structures for LeetCode - Quick Reference Guide

## 1️⃣ List (Array) 📋

**What**: Ordered, mutable collection. Like dynamic arrays - grows/shrinks automatically.

### Creation & Initialization
```python
# Empty list
lst = []                          # ✅ Most common

# With initial values
lst = [1, 2, 3, 4, 5]            # ✅ Quick list
lst = list()                      # List constructor

# With default values
lst = [0] * 5                     # [0, 0, 0, 0, 0]
lst = [[0] * 3 for _ in range(2)]  # 2D: [[0,0,0], [0,0,0]]

# From another iterable
lst = list(range(5))             # [0, 1, 2, 3, 4]
lst = list("abc")                # ['a', 'b', 'c']
```

### Common Operations
```python
lst = [1, 2, 3]

# Access
lst[0]          # 🎯 1 (indexing)
lst[-1]         # 🎯 3 (last element)
lst[0:2]        # 🎯 [1, 2] (slicing)

# Add
lst.append(4)   # ⏱️ O(1) → [1, 2, 3, 4]
lst.insert(0, 0) # ⏱️ O(n) → [0, 1, 2, 3, 4]
lst.extend([4, 5]) # ⏱️ O(n) → [1, 2, 3, 4, 5]

# Remove
lst.pop()       # ⏱️ O(1) (last element)
lst.pop(0)      # ⏱️ O(n) (first element)
lst.remove(2)   # ⏱️ O(n) remove value 2
del lst[0]      # ⏱️ O(n) delete by index

# Search
lst.index(2)    # ⏱️ O(n) → index of 2
2 in lst        # ⏱️ O(n) → True/False
lst.count(2)    # ⏱️ O(n) → count occurrences

# Sort/Reverse
lst.sort()      # ⏱️ O(n log n) → in-place
sorted(lst)     # ⏱️ O(n log n) → new list
lst.reverse()   # ⏱️ O(n) → in-place
```

### Visual Representation
```
List: [1, 2, 3, 4, 5]
      [0][1][2][3][4]  indices
      [-5][-4][-3][-2][-1]  negative indices

Slicing: lst[1:4]
         [1, 2, 3, 4, 5]
            ↓↓↓
         [2, 3, 4]

append() - Add to end O(1):
         [1, 2, 3] → append(4) → [1, 2, 3, 4]

pop() - Remove from end O(1):
         [1, 2, 3, 4] → pop() → [1, 2, 3]

insert(idx, val) - Insert at position O(n):
         [1, 2, 4] → insert(2, 3) → [1, 2, 3, 4]
                          shift remaining ➡️
```

**⏱️ Complexity Summary**:
- Access: O(1)
- Append: O(1) amortized
- Insert/Delete at start: O(n)
- Insert/Delete at end: O(1)
- Search: O(n)
- Sort: O(n log n)

---

## 2️⃣ Tuple (Immutable List) 🔒

**What**: Ordered, immutable collection. Cannot be modified after creation.

### Creation & Initialization
```python
# Create tuple
t = ()                    # Empty tuple
t = (1,)                  # Single element (note comma!)
t = (1, 2, 3)             # Multiple elements
t = tuple([1, 2, 3])      # From list
t = tuple("abc")          # ('a', 'b', 'c')

# Unpacking
a, b, c = (1, 2, 3)       # a=1, b=2, c=3
a, b = 1, 2               # Tuple without parentheses
first, *rest = (1, 2, 3, 4)  # first=1, rest=[2,3,4]
```

### Common Operations
```python
t = (1, 2, 3, 2)

# Access (same as list)
t[0]              # 🎯 1
t[-1]             # 🎯 3
t[0:2]            # 🎯 (1, 2)

# Cannot modify (immutable)
# t[0] = 5        # ❌ TypeError
# t.append(4)     # ❌ No append method

# Read-only operations
t.index(2)        # ⏱️ O(n) → 1
2 in t            # ⏱️ O(n) → True
t.count(2)        # ⏱️ O(n) → 2
len(t)            # ⏱️ O(1) → 4
```

### Why Use Tuples?
```python
# 🎯 Can be used as dictionary keys (hashable)
d = {(1, 2): "point"}     # ✅ Valid
# d = {[1, 2]: "point"}   # ❌ Lists cannot be keys

# 🎯 Function return multiple values
def coords():
    return (10, 20)       # Return tuple

x, y = coords()           # Unpack easily

# 🎯 Prevent accidental modification
coordinates = (5, 10)     # Cannot change accidentally
```

**⏱️ Complexity Summary**:
- All read operations: O(n) or O(1) like lists
- Immutable = safer + hashable (can use as dict key)

---

## 3️⃣ Dictionary (Hash Map) 🗂️

**What**: Unordered collection of key-value pairs. Maps keys to values using hash function.

### Creation & Initialization
```python
# Empty dictionary
d = {}                    # ✅ Most common
d = dict()                # Dict constructor

# With initial values
d = {"a": 1, "b": 2}      # Literal notation
d = dict(a=1, b=2)        # Keyword arguments
d = dict([("a", 1), ("b", 2)])  # From pairs

# Dict comprehension
d = {x: x**2 for x in range(5)}  # {0:0, 1:1, 2:4, ...}

# Default values
from collections import defaultdict
d = defaultdict(int)      # Default value: 0
d = defaultdict(list)     # Default value: []
```

### Common Operations
```python
d = {"a": 1, "b": 2, "c": 3}

# Access
d["a"]            # 🎯 1
d.get("a")        # 🎯 1 (safer, returns None if missing)
d.get("z", 0)     # 🎯 0 (default value if key missing)
d["z"]            # ❌ KeyError (if missing)

# Add/Update
d["d"] = 4        # ⏱️ O(1) average
d.update({"e": 5, "f": 6})  # Add multiple

# Remove
del d["a"]        # ⏱️ O(1) average
d.pop("b")        # ⏱️ O(1) average, returns value
d.pop("z", None)  # Returns None if missing
d.clear()         # ⏱️ O(n) remove all

# Check existence
"a" in d          # ⏱️ O(1) average → True
"z" in d          # ⏱️ O(1) average → False

# Iterate
for key in d:           # Iterate keys
for key, val in d.items():  # Iterate pairs
for val in d.values():  # Iterate values

# Get all keys/values
d.keys()          # dict_keys(['a', 'b', 'c'])
d.values()        # dict_values([1, 2, 3])
d.items()         # dict_items([('a',1), ('b',2), ...])
```

### Visual Representation
```
Dictionary: {"name": "Alice", "age": 30}

             ┌─────────────────────────┐
             │   Hash Table (Internal) │
             ├─────────────────────────┤
    "name"   │ hash → "Alice"          │
    "age"    │ hash → 30               │
             └─────────────────────────┘

Key Lookup - O(1) average:
    Key: "name" → Hash Function → Bucket → Value: "Alice"

DefaultDict Example:
    d = defaultdict(int)
    d["count"] += 1  ✅ No KeyError, defaults to 0
```

**Counter (Specialized Dictionary)**:
```python
from collections import Counter

# Count occurrences
c = Counter("aabbcc")     # Counter({'a': 2, 'b': 2, 'c': 2})
c = Counter([1, 1, 1, 2, 2, 3])  # Counter({1: 3, 2: 2, 3: 1})

# Most common
c.most_common(2)          # [('a', 2), ('b', 2)]

# Access like dict
c["a"]                    # 2
c["z"]                    # 0 (default)
```

**⏱️ Complexity Summary**:
- Access/Insert/Delete: O(1) average, O(n) worst
- Search: O(1) average, O(n) worst
- Iteration: O(n)

---

## 4️⃣ Set 🎯

**What**: Unordered collection of unique elements. Fast membership testing.

### Creation & Initialization
```python
# Empty set (NOT {})
s = set()                 # ✅ Correct empty set
s = {}                    # ❌ This is empty dict!

# With values
s = {1, 2, 3}            # ✅ Literal notation
s = set([1, 2, 2, 3])    # {1, 2, 3} duplicates removed
s = set("abc")           # {'a', 'b', 'c'}

# Set comprehension
s = {x for x in range(5)}  # {0, 1, 2, 3, 4}
```

### Common Operations
```python
s = {1, 2, 3}
t = {2, 3, 4}

# Add/Remove
s.add(4)          # ⏱️ O(1) average
s.update([5, 6])  # ⏱️ O(n) add multiple
s.remove(4)       # ⏱️ O(1) average (error if missing)
s.discard(4)      # ⏱️ O(1) average (no error if missing)
s.pop()           # ⏱️ O(1) remove arbitrary element

# Check membership
2 in s            # ⏱️ O(1) average → True
5 in s            # ⏱️ O(1) average → False

# Set operations
s & t             # ⏱️ O(min(len(s),len(t))) intersection {2, 3}
s | t             # ⏱️ O(len(s)+len(t)) union {1, 2, 3, 4}
s - t             # ⏱️ O(len(s)) difference {1}
s ^ t             # ⏱️ O(len(s)+len(t)) symmetric diff {1, 4}

# Comparisons
s <= t            # Is s subset of t? False
s >= t            # Is s superset of t? False
s == t            # Are they equal? False
```

### Visual Representation
```
Set: {1, 2, 3}

       ┌─────────────────────────┐
       │   Hash Set (Internal)   │
       ├─────────────────────────┤
  1    │ hash → stored           │
  2    │ hash → stored           │
  3    │ hash → stored           │
       └─────────────────────────┘

Add - O(1):
  {1, 2, 3} → add(4) → {1, 2, 3, 4}

Membership - O(1):
  4 in {1, 2, 3, 4} → hash(4) → O(1)

Set Operations:
  {1, 2, 3} & {2, 3, 4} = {2, 3}  (intersection)
  {1, 2, 3} | {2, 3, 4} = {1,2,3,4}  (union)
  {1, 2, 3} - {2, 3, 4} = {1}  (difference)
```

**⏱️ Complexity Summary**:
- Add/Remove/Check: O(1) average, O(n) worst
- Union/Intersection: O(min/max of sizes)
- Iteration: O(n)

---

## 5️⃣ Queue (FIFO) 🚦

**What**: First-In-First-Out. Add to back, remove from front.

### Creation & Initialization
```python
from collections import deque

# Create queue
q = deque()              # ✅ Most efficient
q = deque([1, 2, 3])     # With initial values
# q = Queue()            # ❌ Overkill, slower

# Note: Plain list is inefficient (O(n) for popleft)
# lst = []
# lst.pop(0)  # ❌ O(n) - don't use!
```

### Common Operations
```python
q = deque([1, 2, 3])

# Add (to back)
q.append(4)       # ⏱️ O(1) → deque([1, 2, 3, 4])

# Remove (from front)
q.popleft()       # ⏱️ O(1) → returns 1, deque([2, 3, 4])

# Peek
q[0]              # ⏱️ O(1) front element
len(q)            # ⏱️ O(1) size

# Create and process
while q:
    current = q.popleft()  # Get next item
    # process current
    # maybe add more: q.append(new_item)
```

### Visual Representation
```
Queue (FIFO - First In First Out):

Initial:
       ┌─────────────────────────┐
       │  1  │  2  │  3          │
       └─────────────────────────┘
       ↑                         ↑
    popleft()                append()

After append(4):
       ┌─────────────────────────┐
       │  1  │  2  │  3  │  4    │
       └─────────────────────────┘

After popleft():
       ┌─────────────────────────┐
       │  2  │  3  │  4          │
       └─────────────────────────┘

🎯 Use Cases: BFS, Job scheduling, Load balancing
```

**⏱️ Complexity Summary**:
- Append: O(1)
- Popleft: O(1)
- Access: O(1)

---

## 6️⃣ Stack (LIFO) 📚

**What**: Last-In-First-Out. Add and remove from top.

### Creation & Initialization
```python
# Using list (simpler than deque for stack)
stack = []               # ✅ Simple and efficient

# Using deque (also fine)
from collections import deque
stack = deque()

# Using Queue.LifoQueue (overkill)
# from queue import LifoQueue
# stack = LifoQueue()   # ❌ Too complex for interviews
```

### Common Operations
```python
stack = [1, 2, 3]

# Push (add to top)
stack.append(4)   # ⏱️ O(1) → [1, 2, 3, 4]

# Pop (remove from top)
stack.pop()       # ⏱️ O(1) → returns 4, [1, 2, 3]

# Peek
stack[-1]         # ⏱️ O(1) → top element (3)
len(stack)        # ⏱️ O(1) → size

# Empty check
if stack:         # True if not empty
    top = stack.pop()

# Create and process
while stack:
    current = stack.pop()  # Get top item
    # process current
    # maybe add more: stack.append(new_item)
```

### Visual Representation
```
Stack (LIFO - Last In First Out):

Initial:
       ┌─────────┐
       │    4    │ ← push(5) / pop()
       ├─────────┤
       │    3    │
       ├─────────┤
       │    2    │
       ├─────────┤
       │    1    │
       └─────────┘

After push(5):
       ┌─────────┐
       │    5    │ ← top
       ├─────────┤
       │    4    │
       ├─────────┤
       │    3    │
       ├─────────┤
       │    2    │
       ├─────────┤
       │    1    │
       └─────────┘

After pop():
       ┌─────────┐
       │    4    │ ← top
       ├─────────┤
       │    3    │
       ├─────────┤
       │    2    │
       ├─────────┤
       │    1    │
       └─────────┘

🎯 Use Cases: DFS, Backtracking, Expression evaluation, Undo/Redo
```

**⏱️ Complexity Summary**:
- Append (push): O(1)
- Pop: O(1)
- Access: O(1)

---

## 7️⃣ Heap 🏔️

**What**: Complete binary tree where parent ≤ children (min-heap) or parent ≥ children (max-heap).

### Creation & Initialization
```python
import heapq

# Min-heap (default)
h = []                          # Empty
h = [3, 1, 4, 1, 5]             # Not yet heapified
heapq.heapify(h)                # ⏱️ O(n) → heapify in-place
h = [heapq.heappush(h, x) for x in [3,1,4]]  # Build incrementally

# Max-heap (negate values)
max_h = []
heapq.heappush(max_h, -3)       # Push negative
heapq.heappush(max_h, -1)
# Pop with negation:
max_val = -heapq.heappop(max_h)

# Using class for max-heap clarity
from heapq import heappush, heappop
class MaxHeap:
    def __init__(self):
        self.heap = []
    def push(self, x):
        heappush(self.heap, -x)
    def pop(self):
        return -heappop(self.heap)
```

### Common Operations
```python
h = [1, 3, 2, 5, 4]
heapq.heapify(h)  # Now a valid min-heap

# Add element
heapq.heappush(h, 0)      # ⏱️ O(log n) maintain heap property

# Remove minimum
min_val = heapq.heappop(h)  # ⏱️ O(log n) → 0

# Peek minimum (no standard method!)
min_val = h[0]            # ⏱️ O(1) but don't modify!

# Get n smallest elements
heapq.nsmallest(3, h)     # ⏱️ O(n log k) → [1, 2, 3]
heapq.nlargest(3, h)      # ⏱️ O(n log k) → [5, 4, 3]

# Common pattern: push and pop simultaneously
min_val = heapq.heapreplace(h, x)  # ⏱️ O(log n)
```

### Visual Representation
```
Min-Heap (Parent ≤ Children):

            1          ← smallest at root
         ↙   ↘
        3     2
      ↙ ↘   ↙
     5   4  3

Array representation: [1, 3, 2, 5, 4, 3]
                       0  1  2  3  4  5

Parent-Child relationship:
parent(i) = (i-1)//2
left(i) = 2*i+1
right(i) = 2*i+2

Insert 0 - O(log n):
            1
         ↙   ↘
        3     2         Bubble up if smaller
      ↙ ↘   ↙ ↘
     5   4  3  0

Delete min - O(log n):
Replace root with last element, bubble down

Push(0) → heappop() pattern:
h = [1, 3, 2]
heappush(h, 0)    → [0, 3, 2, 1]
heappop(h)        → 0, heap: [1, 3, 2]

🎯 Use Cases: Priority queues, Dijkstra's algorithm, K-largest/smallest
```

**⏱️ Complexity Summary**:
- Heapify: O(n)
- Push: O(log n)
- Pop: O(log n)
- Peek: O(1)
- Nlargest/Nsmallest: O(n log k)

---

## 8️⃣ Priority Queue (Heap-based) 🎫

**What**: Queue where elements have priorities. Uses heap internally.

### Creation & Initialization
```python
import heapq
from collections import deque

# Simple priority queue (min-heap)
pq = []
heapq.heappush(pq, (priority, item))  # (lower #, higher priority)

# Example: task scheduling
pq = []
heapq.heappush(pq, (1, "urgent"))     # priority 1
heapq.heappush(pq, (2, "normal"))     # priority 2
heapq.heappush(pq, (0, "critical"))   # priority 0

# Practical pattern with counter
import heapq
pq = []
counter = 0

def push_task(priority, task):
    global counter
    heapq.heappush(pq, (priority, counter, task))
    counter += 1

# Handles ties: same priority → FIFO order
```

### Common Operations
```python
pq = []

# Add with priority
heapq.heappush(pq, (3, "task1"))    # ⏱️ O(log n)
heapq.heappush(pq, (1, "task2"))
heapq.heappush(pq, (2, "task3"))

# Get highest priority (lowest number = highest priority)
priority, task = heapq.heappop(pq)  # ⏱️ O(log n) → (1, "task2")

# Size
len(pq)                             # ⏱️ O(1)

# Iterate (but doesn't pop)
for priority, task in pq:
    print(f"Priority: {priority}, Task: {task}")
```

### Visual Representation
```
Priority Queue (Min-Heap):

Insert: (2, "normal"), (1, "urgent"), (0, "critical")

         (0, critical)  ← highest priority (lowest number)
        ↙              ↘
  (2, normal)      (1, urgent)

Process order: critical → urgent → normal

Real-world example - Hospital triage:
  Insert: (3, "mild"), (1, "critical"), (2, "serious")
  
  Get next patient: (1, "critical")
  Get next patient: (2, "serious")
  Get next patient: (3, "mild")
```

**⏱️ Complexity Summary**:
- Push: O(log n)
- Pop (get max): O(log n)
- Peek: O(1)

---

## 9️⃣ String 📝

**What**: Immutable sequence of characters. Core text operations.

### Creation & Initialization
```python
# String literals
s = ""                    # Empty
s = "hello"              # Basic
s = 'hello'              # Single or double quotes
s = """multi
line"""                  # Triple quotes

# String constructor
s = str(123)             # "123"
s = str([1, 2, 3])       # "[1, 2, 3]"

# String from character repeated
s = "a" * 5              # "aaaaa"

# Join multiple strings
s = "".join(["a", "b", "c"])  # ⏱️ O(n) "abc"
```

### Common Operations
```python
s = "hello world"

# Access
s[0]                 # 'h'
s[-1]                # 'd'
s[0:5]               # "hello"
s[6:]                # "world"

# Properties
len(s)               # ⏱️ O(1) → 11
s.upper()            # ⏱️ O(n) → "HELLO WORLD"
s.lower()            # ⏱️ O(n) → "hello world"

# Search
s.find("world")      # ⏱️ O(n) → 6 (index)
s.find("xyz")        # ⏱️ O(n) → -1 (not found)
s.count("l")         # ⏱️ O(n) → 3

# Check
"world" in s         # ⏱️ O(n) → True
s.startswith("hel")  # ⏱️ O(k) where k=len(prefix) → True
s.endswith("rld")    # ⏱️ O(k) → True

# Split/Join
s.split(" ")         # ⏱️ O(n) → ["hello", "world"]
",".join(["a","b"])  # ⏱️ O(n) → "a,b"

# Replace
s.replace("world", "python")  # ⏱️ O(n) → "hello python"

# Strip whitespace
s = "  hello  "
s.strip()            # ⏱️ O(n) → "hello"
s.lstrip()           # ⏱️ O(n) → "hello  "
s.rstrip()           # ⏱️ O(n) → "  hello"
```

### String Methods Cheat Sheet
```python
s = "Hello World"

# Case
s.upper()             # "HELLO WORLD"
s.lower()             # "hello world"
s.capitalize()        # "Hello world"
s.title()             # "Hello World"
s.swapcase()          # "hELLO wORLD"

# Check type
s.isalpha()           # True (only letters)
s.isdigit()           # False (only digits)
s.isalnum()           # True (letters or digits)
s.isspace()           # False (only whitespace)

# Whitespace
s.strip()             # Remove leading/trailing
s.lstrip()            # Remove from left
s.rstrip()            # Remove from right

# Split/Join
s.split()             # ["Hello", "World"] (any whitespace)
s.split(" ")          # ["Hello", "World"] (specific)
"".join(list)         # Join list of strings
```

### String Building (Critical for Performance!)
```python
# ❌ WRONG - O(n²) due to immutability
result = ""
for char in s:
    result += char    # Creates new string each time! 🐢

# ✅ RIGHT - O(n) using list
result = []
for char in s:
    result.append(char)
result = "".join(result)  # 🚀 Fast

# ✅ Concise - List comprehension
result = "".join([process(char) for char in s])
```

**⏱️ Complexity Summary**:
- Access: O(1)
- Search: O(n)
- Slice: O(k) where k=length of slice
- Join: O(n)
- String concatenation (+): O(n) each time, avoid in loops!

---

## 🔟 Linked List 🔗

**What**: Chain of nodes with values and pointers. Manual creation needed.

### Node Definition
```python
# Definition for singly-linked list
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

# Definition for doubly-linked list
class DoublyListNode:
    def __init__(self, val=0, prev=None, next=None):
        self.val = val
        self.prev = prev
        self.next = next
```

### Creation & Initialization
```python
# Create manually
head = ListNode(1)
head.next = ListNode(2)
head.next.next = ListNode(3)

# Visual: 1 → 2 → 3 → None

# Create from list
def create_linked_list(arr):
    if not arr:
        return None
    head = ListNode(arr[0])
    current = head
    for val in arr[1:]:
        current.next = ListNode(val)
        current = current.next
    return head

head = create_linked_list([1, 2, 3])
```

### Common Operations
```python
# Traverse
current = head
while current:
    print(current.val)      # Process node
    current = current.next

# Find element
def find(head, val):
    current = head
    while current:
        if current.val == val:
            return current
        current = current.next
    return None

# Insert at beginning
new_head = ListNode(0)
new_head.next = head

# Insert after node
new_node = ListNode(2.5)
new_node.next = node.next
node.next = new_node

# Delete node
node.next = node.next.next  # Skip next

# Get length
def get_length(head):
    count = 0
    current = head
    while current:
        count += 1
        current = current.next
    return count
```

### Visual Representation
```
Singly Linked List:
1 → 2 → 3 → None
│
head

    current (at 2)
    │
    ↓
1 → 2 → 3 → None

Insert 2.5 between 2 and 3:
Step 1: new_node = ListNode(2.5)
Step 2: new_node.next = node2.next  (3)
Step 3: node2.next = new_node

1 → 2 → 2.5 → 3 → None

Delete 2 (skip it):
Before:
1 → 2 → 3 → None

node1.next = node2.next

After:
1 → 3 → None
```

**⏱️ Complexity Summary**:
- Access: O(n)
- Search: O(n)
- Insert at head: O(1)
- Insert at position: O(n)
- Delete at head: O(1)
- Delete at position: O(n)

---

## 1️⃣1️⃣ Deque (Double-Ended Queue) 🔄

**What**: Queue that allows operations on both ends. Faster than list for both ends.

### Creation & Initialization
```python
from collections import deque

d = deque()               # Empty
d = deque([1, 2, 3])      # With initial values
d = deque([1, 2, 3], maxlen=5)  # Max length (automatic removal)
```

### Common Operations
```python
d = deque([1, 2, 3])

# Add
d.append(4)       # ⏱️ O(1) Add right: [1, 2, 3, 4]
d.appendleft(0)   # ⏱️ O(1) Add left: [0, 1, 2, 3, 4]

# Remove
d.pop()           # ⏱️ O(1) Remove right: [0, 1, 2, 3]
d.popleft()       # ⏱️ O(1) Remove left: [1, 2, 3]

# Access
d[0]              # ⏱️ O(1) First element
d[-1]             # ⏱️ O(1) Last element

# Rotate
d.rotate(1)       # ⏱️ O(n) Rotate right: [3, 1, 2]
d.rotate(-1)      # ⏱️ O(n) Rotate left: [1, 2, 3]

# Clear
d.clear()         # ⏱️ O(n)
```

### Visual Representation
```
Deque: [1, 2, 3]

            appendleft(0)
            │
            ↓
        ┌───────────────┐
        │  0  │  1  │ 2 │ 3
        └───────────────┘
        ↑                ↑
      popleft()      append()
                   (or pop())

Efficient Queue (FIFO):
append()      → add right
popleft()     → remove left

Efficient Stack (LIFO):
append()      → add right
pop()         → remove right

Sliding Window:
d = deque()
for i in range(n):
    d.append(arr[i])
    if len(d) > window_size:
        d.popleft()  ← Maintain window
```

**⏱️ Complexity Summary**:
- Append/Appendleft: O(1)
- Pop/Popleft: O(1)
- Access: O(1)
- Rotate: O(n)

---

## 1️⃣2️⃣ defaultdict & Counter 🎯

**What**: Specialized dictionaries for common use cases.

### defaultdict
```python
from collections import defaultdict

# Specify default factory
d = defaultdict(int)          # Default: 0
d = defaultdict(list)         # Default: []
d = defaultdict(set)          # Default: set()
d = defaultdict(lambda: 0)    # Custom default

# Usage
d["count"] += 1               # No KeyError, starts at 0
d["items"].append(5)          # No KeyError, starts as []

# Example: Group items
d = defaultdict(list)
for key, val in pairs:
    d[key].append(val)
```

### Counter
```python
from collections import Counter

# Count elements
c = Counter([1, 1, 1, 2, 2, 3])  # Counter({1: 3, 2: 2, 3: 1})
c = Counter("aabbcc")             # Counter({'a': 2, 'b': 2, 'c': 2})

# Most common
c.most_common(2)                 # [(1, 3), (2, 2)]
c.most_common(1)[0][0]           # Get most common element: 1

# Arithmetic
c = Counter([1, 1, 1, 2, 2])
d = Counter([2, 2, 3])
c + d                             # Counter({1: 3, 2: 4, 3: 1})
c - d                             # Counter({1: 3})
c & d                             # Counter({2: 2})
c | d                             # Counter({1: 3, 2: 2, 3: 1})

# Access like dict
c[1]                              # 3
c[999]                            # 0 (default)
```

---

## ⏱️ Quick Complexity Reference Table

| **Data Structure** | **Access** | **Insert** | **Delete** | **Search** |
|------------------|----------|-----------|----------|----------|
| **List** | O(1) | O(n) | O(n) | O(n) |
| **Tuple** | O(1) | N/A | N/A | O(n) |
| **Dict** | O(1) | O(1) | O(1) | O(1) |
| **Set** | N/A | O(1) | O(1) | O(1) |
| **Queue** | O(1) | O(1) | O(1) | N/A |
| **Stack** | O(1) | O(1) | O(1) | N/A |
| **Heap** | O(1) | O(log n) | O(log n) | O(n) |
| **LinkedList** | O(n) | O(1)* | O(1)* | O(n) |

*At known position/head

---

## 🎯 Interview Cheat Sheet

```python
# Initialization patterns
lst = []                           # List
d = {}                             # Dict
s = set()                          # Set (NOT {})
st = []                            # Stack
q = deque()                        # Queue
h = []  # heapq.heappush(h, x)    # Heap
from collections import Counter
from collections import defaultdict
from collections import deque

# Common operations
lst.append(x)                      # Add to list
lst.pop()                          # Remove from list
d[key] = val                       # Dict assignment
s.add(x)                           # Add to set
st.pop()                           # Stack pop
q.popleft()                        # Queue dequeue
heapq.heappush(h, x)              # Heap push
heapq.heappop(h)                  # Heap pop

# Iteration
for x in lst:                      # Iterate list
for k, v in d.items():            # Iterate dict
for x in s:                        # Iterate set
while st:  st.pop()               # While stack not empty
while q:   q.popleft()            # While queue not empty

# String building (FAST!)
result = "".join([str(x) for x in lst])

# List comprehension
result = [x*2 for x in range(10)]  # [0, 2, 4, ...]

# Dictionary comprehension
d = {x: x**2 for x in range(5)}    # {0: 0, 1: 1, 2: 4, ...}

# Set comprehension
s = {x for x in lst}               # Remove duplicates

# Tuple unpacking
a, b = (1, 2)
a, b, c = some_func()              # Return multiple values
first, *rest = lst                 # first element + rest
```

---

## 🚀 Performance Tips for Interviews

```python
# ✅ DO:
result = []
for x in lst:
    result.append(process(x))
return "".join(result)            # O(n) string building

# ❌ DON'T:
result = ""
for x in lst:
    result += process(x)          # O(n²) - avoid!

# ✅ DO:
s = set(lst)
if x in s:  ...                   # O(1) lookup

# ❌ DON'T:
if x in lst:  ...                 # O(n) lookup

# ✅ DO:
from collections import deque
q = deque([1,2,3])
q.popleft()                       # O(1)

# ❌ DON'T:
lst = [1,2,3]
lst.pop(0)                        # O(n) - slow!

# ✅ DO:
c = Counter(lst)
most_common = c.most_common(1)[0][0]  # Efficient

# ❌ DON'T:
max_count = 0
for x in set(lst):
    count = lst.count(x)          # O(n) each - slow!
```

---

## 🎊 Summary

| **Need** | **Use This** | **Why** |
|---------|------------|--------|
| **Ordered, flexible size** | `list` | O(1) append, easy to use |
| **Immutable, hashable** | `tuple` | Safe, can use as dict key |
| **Key-value storage** | `dict` | O(1) lookup, very fast |
| **Unique elements** | `set` | O(1) membership, duplicates removed |
| **FIFO queue** | `deque` | O(1) both ends with popleft() |
| **LIFO stack** | `list` | O(1) append/pop, simple |
| **Priority queue** | `heapq` | O(log n) get min/max |
| **Frequency counting** | `Counter` | Efficient, built-in methods |
| **Default values** | `defaultdict` | Avoid KeyError |
| **Linked operations** | `ListNode` | Define your own class |

Good luck with your interview! 🚀
