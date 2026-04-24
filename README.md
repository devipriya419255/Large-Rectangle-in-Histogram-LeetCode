# 📊 LeetCode 84: Largest Rectangle in Histogram (C Solution)

A high-performance C implementation for calculating the largest rectangular area in a histogram. This solution uses a **Monotonic Stack** to identify the boundaries of every possible rectangle in a single linear pass.

## 📖 Problem Description
Given an array of integers `heights` representing the histogram's bar height where the width of each bar is 1, return the area of the largest rectangle in the histogram.

**Example:**
- **Input:** `heights = [2,1,5,6,2,3]`
- **Output:** `10`
- **Logic:** The largest rectangle is formed by bars `5` and `6` with a width of `2` (Area = 10).

## 🛠️ Technical Approach
The solution employs a **Monotonic Increasing Stack** strategy:

1.  **Monotonicity:** We store indices in the stack such that `heights[stack[top]]` is always increasing.
2.  **Triggering Calculation:** When we encounter a bar shorter than the bar at the stack's top, it means the bar at the top cannot extend any further to the right. 
3.  **Boundary Determination:** 
    - **Height:** The height of the popped bar.
    - **Width:** The distance between the current index (`i`) and the new stack top (left boundary).
4.  **Sentinel Value:** The loop runs to `heightsSize`. At `i == heightsSize`, we treat the height as `0` to ensure all remaining bars in the stack are processed and calculated.

## 📊 Complexity Analysis
- **Time Complexity:** **$O(n)$** — Each index is pushed and popped exactly once.
- **Space Complexity:** **$O(n)$** — In the worst case (strictly increasing heights), the stack will store all $n$ indices.

## 🚀 How to Run
1.  Save the code to `histogram.c`.
2.  Compile using:
    ```bash
    gcc -O3 histogram.c -o histogram
    ```
3.  The `largestRectangleArea` function is ready for integration into any C-based performance test.
