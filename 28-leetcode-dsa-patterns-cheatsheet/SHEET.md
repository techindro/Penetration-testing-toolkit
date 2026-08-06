# 💡 Module 28: 100-Day LeetCode & DSA Master Roadmap (C++ & Java)

> [!TIP]
> 🧠 **100-Day Coding Strategy:** Master 1 DSA Pattern per week. Understand the **Approach Transformation** (from Brute Force $O(n^2)$ to Optimal $O(n)$) before writing code. Both C++ and Java solutions are provided below.

---

## 📅 100-Day Day-by-Day DSA Study Schedule

| Day Range | Topic / DSA Pattern | Key Target Problems | Approach Goal |
| :-: | :--- | :--- | :--- |
| **Days 1 - 10** | **Arrays & Two Pointers** | Two Sum, 3Sum, Container With Most Water, Sort Colors | $O(n^2)$ Nested Loops ➔ $O(n)$ Two Pointers |
| **Days 11 - 20** | **Sliding Window & Prefix Sum** | Max Subarray K, Longest Substring Without Repeating, Fruit Into Baskets | $O(n \cdot k)$ Subarrays ➔ $O(n)$ Window Shift |
| **Days 21 - 30** | **Fast & Slow Pointers & Linked List** | Linked List Cycle, Middle of List, Reverse Linked List | $O(n)$ Hash Set Space ➔ $O(1)$ Floyd's Pointers |
| **Days 31 - 40** | **Stacks & Monotonic Stack** | Valid Parentheses, Next Greater Element, Daily Temperatures | $O(n^2)$ Lookahead ➔ $O(n)$ Monotonic Stack |
| **Days 41 - 50** | **Binary Search & Search Space** | Binary Search, Search in Rotated Array, Koko Eating Bananas | $O(n)$ Linear Search ➔ $O(\log n)$ Binary Search |
| **Days 51 - 60** | **Trees & Binary Search Trees** | Inorder/Preorder, Maximum Depth, Lowest Common Ancestor, Validate BST | Recursion DFS & Queue BFS Level Order |
| **Days 61 - 70** | **Heaps & Priority Queue** | Kth Largest Element, Top K Frequent Elements, Merge K Sorted Lists | $O(n \log n)$ Full Sort ➔ $O(n \log k)$ Min/Max Heap |
| **Days 71 - 80** | **Graph Traversal & Algorithms** | Number of Islands, Clone Graph, Course Schedule, Dijkstra's Shortest Path | Matrix BFS/DFS, Topological Sort, Union-Find |
| **Days 81 - 90** | **Dynamic Programming (1D & 2D)** | Climbing Stairs, House Robber, Coin Change, Longest Common Subsequence | $O(2^n)$ Exponential ➔ $O(n)$ Memoization/DP Table |
| **Days 91 - 100** | **Backtracking & Tries** | Subsets, Permutations, N-Queens, Implement Trie (Prefix Tree) | State Space Tree Pruning & Prefix Match |

---

## ⚡ Pattern 1: Two Pointers (Target Sum Pair Search)

### 💡 Approach Breakdown:
- **Brute Force Approach ($O(n^2)$ Time, $O(1)$ Space):** Use two nested loops to check every pair `nums[i] + nums[j] == target`.
- **Optimal Two Pointers Approach ($O(n)$ Time, $O(1)$ Space):** Sort array. Place `left` pointer at index 0 and `right` pointer at end. If sum $< \text{target}$, move `left++`. If sum $> \text{target}$, move `right--`.

#### C++ Code:
```cpp
#include <vector>
#include <algorithm>
using namespace std;

vector<int> twoSumTwoPointers(vector<int>& nums, int target) {
    int left = 0, right = nums.size() - 1;
    while (left < right) {
        int sum = nums[left] + nums[right];
        if (sum == target) return {left, right};
        else if (sum < target) left++;
        else right--;
    }
    return {};
}
```

#### Java Code:
```java
public class Solution {
    public int[] twoSumTwoPointers(int[] nums, int target) {
        int left = 0, right = nums.length - 1;
        while (left < right) {
            int sum = nums[left] + nums[right];
            if (sum == target) return new int[]{left, right};
            else if (sum < target) left++;
            else right--;
        }
        return new int[]{};
    }
}
```

---

## 🪟 Pattern 2: Sliding Window (Max Subarray of Size K)

### 💡 Approach Breakdown:
- **Brute Force Approach ($O(n \cdot k)$ Time):** Re-sum all $k$ elements for every single starting index.
- **Optimal Sliding Window Approach ($O(n)$ Time):** Compute sum of first window of size $k$. Slide window right by adding next element and subtracting left element out of window.

#### C++ Code:
```cpp
#include <vector>
#include <algorithm>
using namespace std;

int maxSubarraySum(const vector<int>& nums, int k) {
    int window_sum = 0;
    for (int i = 0; i < k; ++i) window_sum += nums[i];
    
    int max_sum = window_sum;
    for (size_t i = k; i < nums.size(); ++i) {
        window_sum += nums[i] - nums[i - k];
        max_sum = max(max_sum, window_sum);
    }
    return max_sum;
}
```

#### Java Code:
```java
public class Solution {
    public int maxSubarraySum(int[] nums, int k) {
        int windowSum = 0;
        for (int i = 0; i < k; i++) windowSum += nums[i];
        
        int maxSum = windowSum;
        for (int i = k; i < nums.length; i++) {
            windowSum += nums[i] - nums[i - k];
            maxSum = Math.max(maxSum, windowSum);
        }
        return maxSum;
    }
}
```

---

## 🐢 Pattern 3: Fast & Slow Pointers (Floyd's Cycle Detection)

### 💡 Approach Breakdown:
- **Brute Force Approach ($O(n)$ Space):** Use Hash Set to record visited node pointers.
- **Optimal Floyd's Pointer Approach ($O(1)$ Space):** Move `slow` pointer by 1 step and `fast` pointer by 2 steps. If cycle exists, `fast` will meet `slow`.

#### C++ Code:
```cpp
struct ListNode {
    int val;
    ListNode *next;
    ListNode(int x) : val(x), next(nullptr) {}
};

bool hasCycle(ListNode *head) {
    ListNode *slow = head, *fast = head;
    while (fast && fast->next) {
        slow = slow->next;
        fast = fast->next->next;
        if (slow == fast) return true;
    }
    return false;
}
```

#### Java Code:
```java
class ListNode {
    int val;
    ListNode next;
    ListNode(int x) { val = x; next = null; }
}

public class Solution {
    public boolean hasCycle(ListNode head) {
        ListNode slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            if (slow == fast) return true;
        }
        return false;
    }
}
```

---

## 📚 Pattern 4: Monotonic Stack (Next Greater Element)

### 💡 Approach Breakdown:
- **Brute Force Approach ($O(n^2)$ Time):** Run inner loop for every element to search forward for greater value.
- **Optimal Monotonic Stack Approach ($O(n)$ Time):** Use stack to store indices in monotonic decreasing order of values.

#### C++ Code:
```cpp
#include <vector>
#include <stack>
using namespace std;

vector<int> nextGreaterElement(const vector<int>& nums) {
    int n = nums.size();
    vector<int> res(n, -1);
    stack<int> st;
    for (int i = 0; i < n; ++i) {
        while (!st.empty() && nums[st.top()] < nums[i]) {
            res[st.top()] = nums[i];
            st.pop();
        }
        st.push(i);
    }
    return res;
}
```

#### Java Code:
```java
import java.util.Stack;

public class Solution {
    public int[] nextGreaterElement(int[] nums) {
        int n = nums.length;
        int[] res = new int[n];
        java.util.Arrays.fill(res, -1);
        Stack<Integer> st = new Stack<>();
        
        for (int i = 0; i < n; i++) {
            while (!st.isEmpty() && nums[st.peek()] < nums[i]) {
                res[st.pop()] = nums[i];
            }
            st.push(i);
        }
        return res;
    }
}
```

---

## 🧗 Pattern 5: Dynamic Programming (Climbing Stairs 1D DP)

### 💡 Approach Breakdown:
- **Brute Force Recursive ($O(2^n)$ Time):** $f(n) = f(n-1) + f(n-2)$, causes exponential duplicate subtree computations.
- **Optimal Tabulation DP ($O(n)$ Time, $O(1)$ Space):** Track previous 2 values `prev1` and `prev2`.

#### C++ Code:
```cpp
int climbStairs(int n) {
    if (n <= 2) return n;
    int prev2 = 1, prev1 = 2;
    for (int i = 3; i <= n; ++i) {
        int current = prev1 + prev2;
        prev2 = prev1;
        prev1 = current;
    }
    return prev1;
}
```

#### Java Code:
```java
public class Solution {
    public int climbStairs(int n) {
        if (n <= 2) return n;
        int prev2 = 1, prev1 = 2;
        for (int i = 3; i <= n; i++) {
            int current = prev1 + prev2;
            prev2 = prev1;
            prev1 = current;
        }
        return prev1;
    }
}
```
