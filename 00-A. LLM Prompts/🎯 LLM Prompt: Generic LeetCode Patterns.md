<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" class="logo" width="120"/>

# 🎯 LLM Prompt: Generic LeetCode Pattern Guide Generator

Here's a comprehensive LLM prompt template you can use to generate detailed coding pattern guides for any LeetCode pattern:

## **MASTER PROMPT TEMPLATE**


# 🔀 [PATTERN_NAME] Pattern - Complete Interview Guide

Create a comprehensive interview guide for the **[PATTERN_NAME]** coding pattern following this exact structure and style:

## 📋 REQUIRED STRUCTURE & CONTENT:

### 1️⃣ **Pattern Overview**
- Define the pattern with core concept (Input → Process → Output)
- Explain when and why to use this pattern
- Include time/space complexity overview

### 2️⃣ **Pattern Recognition & Detection**
- Provide clear rules for identifying when to use this pattern
- Include key problem signals and keywords
- Create ASCII visual diagrams showing the pattern concept
- Use emojis liberally in diagrams (🎯, 📊, ✅, ❌, 🔄, etc.)

### 3️⃣ **Standard Algorithm Template**
- Provide a complete Python code template
- Add numbered step comments (1️⃣, 2️⃣, 3️⃣, 4️⃣)
- Include emoji comments in code (# 🎯, # 🔄, # ✅, etc.)

### 4️⃣ **Common Interview Problem Types (5-6 problems)**
- List 5-6 classic problems using this pattern
- For each: Problem name (LC number), difficulty, key technique
- Use format: "**1️⃣ Problem Name (LC XXX)** - Brief description - **Key insight**: Main approach"

### 5️⃣ **Advanced Techniques (3-4 variations)**
For each advanced technique, provide:

#### **🔬 Detailed Breakdown**
- Explain when to use this variation
- Provide complete implementation with detailed comments
- Include step-by-step visual walkthrough with ASCII diagrams

#### **💻 Complete Coding Examples (3-4 per technique)**
- Full working code for 3-4 LeetCode problems
- Each with proper variable names and comments
- Include complexity analysis

#### **📊 Visual Examples**
- ASCII timeline/process diagrams showing algorithm execution
- Use emojis to represent different states/elements

#### **🎯 Problem Examples List**
- List 4-5 problems that use this specific technique
- Format: "**1️⃣ Problem Name (LC XXX)** - Brief description - **Key insight**: Specific approach"

### 6️⃣ **Comprehensive Comparison Table**  
Create a detailed table comparing all techniques with columns:
- 🎯 **Approach** 
- ⏰ **Time Complexity**
- 💾 **Space Complexity** 
- 🛠️ **Best Use Cases**
- 📝 **Key Insights**
- 🎪 **Template Pattern**

### 7️⃣ **Problem-to-Approach Mapping**
Table showing which technique to use for different problem types:
- **Problem Type** | **🥇 Primary** | **🥈 Secondary** | **🥉 Alternative** | **Example Problems**

### 8️⃣ **Performance Characteristics**
Table showing performance across different data sizes with ✅/⚠️ indicators

### 9️⃣ **Selection Decision Tree**
ASCII tree diagram showing how to choose between techniques:
```

📋 Problem Analysis:
│
├─ 🔍 Condition 1?
│   └─ ✅ Use Technique A
│
├─ 🔍 Condition 2?
│   └─ ✅ Use Technique B

```

### 🔟 **Common Pitfalls Analysis**
- Show a WRONG code example with detailed bug analysis
- Break down 3-4 critical bugs with explanations
- Include execution trace table showing incorrect vs expected output
- Provide correct solutions comparison table

### 1️⃣1️⃣ **Interview Success Tips**
- Problem recognition signals
- Optimization strategies table
- Common edge cases with code examples  
- Debug checklist with ✅ items

### 1️⃣2️⃣ **ASCII Problem Solving Flow**
Step-by-step visual walkthrough of solving a sample problem with:
- Input visualization with emojis
- Each step with visual representation
- Final result with emoji diagrams

### 1️⃣3️⃣ **Master Problem Set**
Table with Problem | Difficulty | Key Technique

### 1️⃣4️⃣ **Memory Aids**
- Memorable mnemonics with emojis
- Key formulas or conditions
- Pattern-specific reminders

## 📝 STYLE REQUIREMENTS:

### **Emojis & Visual Elements:**
- Use emojis liberally throughout (🔀, 🎯, 📊, ✅, ❌, 🔄, 📝, 🏆, 💡, 🚀, etc.)
- Start section headers with relevant emojis
- Use emojis in ASCII diagrams and code comments
- Create visual representations with emoji symbols

### **Formatting:**
- Use Markdown with proper headers (#, ##, ###)
- Bold important concepts sparingly (**key terms**)
- Use code blocks with Python syntax highlighting
- Create tables for comparisons
- Use bullet points and numbered lists appropriately

### **ASCII Diagrams:**
- Create visual representations using text and emojis
- Show algorithm execution steps visually
- Use emojis to represent different states/elements
- Include timeline visualizations where applicable

### **Tone & Style:**
- Conversational and engaging
- Technical but accessible
- Interview-focused practical advice
- Include specific LeetCode problem numbers
- End with motivational statement about interview success

### **Code Examples:**
- All code in Python
- Include detailed comments with emojis
- Show complete working implementations
- Add complexity analysis
- Use descriptive variable names

## Tips
- 🎯 Be Specific: "Focus extra attention on variations"
- 📊 Customize Difficulty: "Include more advanced problems for senior-level interviews" and also "Focus on beginner-friendly explanations"
- 🔍 Pattern Combinations: Give me hybrid pattern guides, for example here are some combinations:"Two Pointers + Sliding Window" or "Heap + Greedy" etc. 
- 📝 Interview Level: "Tailor for FAANG interview preparation" and "Include system design considerations"

Now create the complete guide for the **[PATTERN_NAME]** pattern following this exact structure and style.



## 🎯 **How to Use This Prompt**

Simply replace `[PATTERN_NAME]` with any coding pattern you want to learn:

### **Examples:**

- `[PATTERN_NAME]` = "Two Pointers"
- `[PATTERN_NAME]` = "Sliding Window"
- `[PATTERN_NAME]` = "Binary Search"
- `[PATTERN_NAME]` = "Backtracking"
- `[PATTERN_NAME]` = "Dynamic Programming"
- `[PATTERN_NAME]` = "Tree Traversal"
- `[PATTERN_NAME]` = "Graph BFS/DFS"
- `[PATTERN_NAME]` = "Heap/Priority Queue"
- `[PATTERN_NAME]` = "Stack/Monotonic Stack"
- `[PATTERN_NAME]` = "Trie"
- `[PATTERN_NAME]` = "Union Find"


### **Sample Usage:**

```
# 🔀 Two Pointers Pattern - Complete Interview Guide

Create a comprehensive interview guide for the **Two Pointers** coding pattern following this exact structure and style:
[... rest of prompt ...]
```


## 🚀 **Pro Tips for Best Results**

1. **🎯 Be Specific**: When using the prompt, you can add specific focus areas like "Focus extra attention on fast/slow pointer variations"
2. **📊 Customize Difficulty**: Add "Include more advanced problems for senior-level interviews" or "Focus on beginner-friendly explanations"
3. **🔍 Pattern Combinations**: Try "Two Pointers + Sliding Window" or "Heap + Greedy" for hybrid pattern guides
4. **📝 Interview Level**: Add "Tailor for FAANG interview preparation" or "Include system design considerations"

This prompt template will generate comprehensive, emoji-rich, visually engaging guides that match the structure and quality of the merge intervals guide you saw! 🎉

