# 💡 Module 28: 100-Day 100-Question LeetCode Practice Plan (C++ & Java)

> [!TIP]
> 🧠 **100 Days = 100 LeetCode Questions:** Practice 1 problem per day pattern-wise. Understand the **Approach Transformation** (from Brute Force $O(n^2)$ to Optimal $O(n)$). Simple real-life memory analogies and working C++ & Java code solutions are provided below.

---

## 🧠 Real-Life Memory Tricks for DSA Patterns (Easy to Remember)

| DSA Pattern | Real-Life Memory Analogy | When to Apply (Trigger) |
| :--- | :--- | :--- |
| **1. Two Pointers** | Two friends starting at opposite ends of a hallway walking towards each other. | Sorted array + Target sum / Pair search. |
| **2. Sliding Window** | Looking through a sliding glass window on a moving train. | Subarray / Substring asking for Min/Max length. |
| **3. Fast & Slow Pointers** | Fast runner & slow jogger on a circular track—the fast runner laps the slow runner. | Linked List cycle detection or finding middle node. |
| **4. Monotonic Stack** | Tall people standing in line blocking the view of shorter people behind them. | Finding Next Greater or Next Smaller Element. |
| **5. Binary Search** | Playing "Guess a Number between 1 and 100" (Higher / Lower guesses). | Sorted search space or Min/Max feasibility. |
| **6. Breadth-First Search (BFS)** | Water ripples expanding outward in concentric circles when dropping a pebble in a pond. | Shortest path in unweighted graph / Level order. |
| **7. Depth-First Search (DFS)** | Exploring a deep maze as far as possible down one path before backtracking. | Connected components / Island problems. |
| **8. Dynamic Programming** | Writing $1+1+1=3$ on paper. Add $+1$ ➔ You don't recount $1+1+1$, you remember $3$ and add $1=4$. | Overlapping subproblems + Counting ways / Min cost. |

---

## 📅 Complete 100-Day Day-by-Day Question Schedule (Day 1 to Day 100)

### 🔹 Phase 1: Two Pointers Pattern (Days 1 - 10)
| Day | Problem # | Problem Name | Difficulty | Core Pattern |
| :-: | :-: | :--- | :-: | :--- |
| **Day 1** | #1 | Two Sum | Easy | Two Pointers / Hash Map |
| **Day 2** | #167 | Two Sum II - Input Array Is Sorted | Medium | Two Pointers |
| **Day 3** | #15 | 3Sum | Medium | Sorting + Two Pointers |
| **Day 4** | #18 | 4Sum | Medium | Two Pointers |
| **Day 5** | #11 | Container With Most Water | Medium | Two Pointers (Shrink Boundary) |
| **Day 6** | #42 | Trapping Rain Water | Hard | Two Pointers / Dynamic Programming |
| **Day 7** | #26 | Remove Duplicates from Sorted Array | Easy | Two Pointers (In-place) |
| **Day 8** | #283 | Move Zeroes | Easy | Two Pointers (In-place Swap) |
| **Day 9** | #75 | Sort Colors (Dutch National Flag) | Medium | 3-Pointers Partition |
| **Day 10** | #977 | Squares of a Sorted Array | Easy | Two Pointers (Extreme Ends) |

---

### 🔹 Phase 2: Sliding Window Pattern (Days 11 - 20)
| Day | Problem # | Problem Name | Difficulty | Core Pattern |
| :-: | :-: | :--- | :-: | :--- |
| **Day 11** | #643 | Maximum Average Subarray I | Easy | Fixed Sliding Window |
| **Day 12** | #3 | Longest Substring Without Repeating Characters | Medium | Variable Sliding Window |
| **Day 13** | #424 | Longest Repeating Character Replacement | Medium | Sliding Window + Frequency Map |
| **Day 14** | #1004 | Max Consecutive Ones III | Medium | Sliding Window (At most K zeros) |
| **Day 15** | #567 | Permutation in String | Medium | Fixed Window Hash Match |
| **Day 16** | #76 | Minimum Window Substring | Hard | Sliding Window Expand/Contract |
| **Day 17** | #209 | Minimum Size Subarray Sum | Medium | Dynamic Window Sum |
| **Day 18** | #904 | Fruit Into Baskets | Medium | 2-Category Sliding Window |
| **Day 19** | #438 | Find All Anagrams in a String | Medium | Fixed Window Anagram Count |
| **Day 20** | #1456 | Max Number of Vowels in Substring of Given Length | Medium | Fixed Window Vowel Count |

---

### 🔹 Phase 3: Fast & Slow Pointers & Linked Lists (Days 21 - 30)
| Day | Problem # | Problem Name | Difficulty | Core Pattern |
| :-: | :-: | :--- | :-: | :--- |
| **Day 21** | #141 | Linked List Cycle | Easy | Fast & Slow Pointers |
| **Day 22** | #142 | Linked List Cycle II | Medium | Floyd's Cycle Entry Detection |
| **Day 23** | #876 | Middle of the Linked List | Easy | Fast & Slow Pointers |
| **Day 24** | #202 | Happy Number | Easy | Fast & Slow Pointers Cycle |
| **Day 25** | #234 | Palindrome Linked List | Easy | Reverse Half & Compare |
| **Day 26** | #206 | Reverse Linked List | Easy | Iterative Pointer Reversal |
| **Day 27** | #92 | Reverse Linked List II | Medium | Sub-list Pointer Reversal |
| **Day 28** | #21 | Merge Two Sorted Lists | Easy | Two Pointers Link Merge |
| **Day 29** | #19 | Remove Nth Node From End of List | Medium | Two Pointers Gap |
| **Day 30** | #143 | Reorder List | Medium | Find Mid + Reverse + Merge |

---

### 🔹 Phase 4: Stacks & Monotonic Stack (Days 31 - 40)
| Day | Problem # | Problem Name | Difficulty | Core Pattern |
| :-: | :-: | :--- | :-: | :--- |
| **Day 31** | #20 | Valid Parentheses | Easy | Stack Matching |
| **Day 32** | #155 | Min Stack | Medium | Auxiliary Min Stack |
| **Day 33** | #150 | Evaluate Reverse Polish Notation | Medium | Stack Arithmetic |
| **Day 34** | #739 | Daily Temperatures | Medium | Monotonic Decreasing Stack |
| **Day 35** | #496 | Next Greater Element I | Easy | Monotonic Stack + Hash Map |
| **Day 36** | #503 | Next Greater Element II | Medium | Circular Monotonic Stack |
| **Day 37** | #84 | Largest Rectangle in Histogram | Hard | Monotonic Stack Area |
| **Day 38** | #85 | Maximal Rectangle | Hard | 2D Histogram Monotonic Stack |
| **Day 39** | #394 | Decode String | Medium | Stack String Expansion |
| **Day 40** | #71 | Simplify Path | Medium | Stack Path Normalization |

---

### 🔹 Phase 5: Binary Search & Search Space (Days 41 - 50)
| Day | Problem # | Problem Name | Difficulty | Core Pattern |
| :-: | :-: | :--- | :-: | :--- |
| **Day 41** | #704 | Binary Search | Easy | Standard Binary Search |
| **Day 42** | #35 | Search Insert Position | Easy | Binary Search Lower Bound |
| **Day 43** | #74 | Search a 2D Matrix | Medium | Binary Search 2D Indexing |
| **Day 44** | #162 | Find Peak Element | Medium | Binary Search on Slope |
| **Day 45** | #33 | Search in Rotated Sorted Array | Medium | Rotated Binary Search |
| **Day 46** | #153 | Find Minimum in Rotated Sorted Array | Medium | Binary Search Minimum Pivot |
| **Day 47** | #875 | Koko Eating Bananas | Medium | Binary Search on Answer |
| **Day 48** | #1011 | Capacity To Ship Packages Within D Days | Medium | Binary Search on Answer |
| **Day 49** | #4 | Median of Two Sorted Arrays | Hard | Binary Search Partition |
| **Day 50** | #154 | Find Minimum in Rotated Sorted Array II | Hard | Binary Search with Duplicates |

---

### 🔹 Phase 6: Binary Trees & BST (Days 51 - 60)
| Day | Problem # | Problem Name | Difficulty | Core Pattern |
| :-: | :-: | :--- | :-: | :--- |
| **Day 51** | #94 | Binary Tree Inorder Traversal | Easy | Tree DFS Traversal |
| **Day 52** | #104 | Maximum Depth of Binary Tree | Easy | Recursive Tree Depth |
| **Day 53** | #226 | Invert Binary Tree | Easy | Tree Pointer Swap |
| **Day 54** | #101 | Symmetric Tree | Easy | Mirror Tree Comparison |
| **Day 55** | #543 | Diameter of Binary Tree | Easy | Tree Height Accumulation |
| **Day 56** | #110 | Balanced Binary Tree | Easy | Depth Check Balance |
| **Day 57** | #236 | Lowest Common Ancestor of a Binary Tree | Medium | Tree Postorder Traversal |
| **Day 58** | #102 | Binary Tree Level Order Traversal | Medium | Queue BFS Level Order |
| **Day 59** | #98 | Validate Binary Search Tree | Medium | Range Bounds BST Check |
| **Day 60** | #230 | Kth Smallest Element in a BST | Medium | Inorder BST Traversal |

---

### 🔹 Phase 7: Heaps & Priority Queue (Days 61 - 70)
| Day | Problem # | Problem Name | Difficulty | Core Pattern |
| :-: | :-: | :--- | :-: | :--- |
| **Day 61** | #215 | Kth Largest Element in an Array | Medium | Min-Heap / QuickSelect |
| **Day 62** | #347 | Top K Frequent Elements | Medium | Min-Heap Frequency |
| **Day 63** | #973 | K Closest Points to Origin | Medium | Max-Heap Distance |
| **Day 64** | #703 | Kth Largest Element in a Stream | Easy | Streaming Min-Heap |
| **Day 65** | #621 | Task Scheduler | Medium | Max-Heap Task Frequency |
| **Day 66** | #295 | Find Median from Data Stream | Hard | Two Heaps (Min + Max) |
| **Day 67** | #23 | Merge k Sorted Lists | Hard | Min-Heap Head Nodes |
| **Day 68** | #373 | Find K Pairs with Smallest Sums | Medium | Min-Heap Pair Sums |
| **Day 69** | #1834 | Single-Threaded CPU | Medium | Priority Queue CPU Queue |
| **Day 70** | #451 | Sort Characters By Frequency | Medium | Priority Queue Sorting |

---

### 🔹 Phase 8: Graphs & Traversals (Days 71 - 80)
| Day | Problem # | Problem Name | Difficulty | Core Pattern |
| :-: | :-: | :--- | :-: | :--- |
| **Day 71** | #200 | Number of Islands | Medium | Grid DFS/BFS Traversal |
| **Day 72** | #695 | Max Area of Island | Medium | Grid Area DFS |
| **Day 73** | #133 | Clone Graph | Medium | Graph HashMap Copy |
| **Day 74** | #207 | Course Schedule | Medium | Topological Sort / Cycle Check |
| **Day 75** | #210 | Course Schedule II | Medium | Kahn's Algorithm BFS |
| **Day 76** | #547 | Number of Provinces | Medium | Disjoint Set Union (DSU) |
| **Day 77** | #994 | Rotting Oranges | Medium | Multi-Source BFS |
| **Day 78** | #743 | Network Delay Time | Medium | Dijkstra Shortest Path |
| **Day 79** | #684 | Redundant Connection | Medium | Union-Find Cycle Check |
| **Day 80** | #127 | Word Ladder | Hard | Shortest Path BFS Transformation |

---

### 🔹 Phase 9: Dynamic Programming (Days 81 - 90)
| Day | Problem # | Problem Name | Difficulty | Core Pattern |
| :-: | :-: | :--- | :-: | :--- |
| **Day 81** | #70 | Climbing Stairs | Easy | 1D Dynamic Programming |
| **Day 82** | #198 | House Robber | Medium | Non-adjacent DP Sum |
| **Day 83** | #213 | House Robber II | Medium | Circular Array DP |
| **Day 84** | #322 | Coin Change | Medium | Unbounded Knapsack DP |
| **Day 85** | #518 | Coin Change II | Medium | Combination DP Ways |
| **Day 86** | #300 | Longest Increasing Subsequence | Medium | 1D LIS DP / Binary Search |
| **Day 87** | #1143 | Longest Common Subsequence | Medium | 2D Grid Match DP |
| **Day 88** | #62 | Unique Paths | Medium | 2D Grid Grid Navigation |
| **Day 89** | #416 | Partition Equal Subset Sum | Medium | 0/1 Knapsack DP |
| **Day 90** | #72 | Edit Distance | Hard | 2D String Transformation DP |

---

### 🔹 Phase 10: Backtracking, Bit Manipulation & Tries (Days 91 - 100)
| Day | Problem # | Problem Name | Difficulty | Core Pattern |
| :-: | :-: | :--- | :-: | :--- |
| **Day 91** | #78 | Subsets | Medium | Backtracking Power Set |
| **Day 92** | #90 | Subsets II | Medium | Backtracking Duplicates |
| **Day 93** | #46 | Permutations | Medium | Backtracking Permutation |
| **Day 94** | #39 | Combination Sum | Medium | Backtracking Re-use Elements |
| **Day 95** | #51 | N-Queens | Hard | Backtracking Board Constraint |
| **Day 96** | #136 | Single Number | Easy | Bitwise XOR |
| **Day 97** | #191 | Number of 1 Bits | Easy | Bitwise AND & Shift |
| **Day 98** | #208 | Implement Trie (Prefix Tree) | Medium | Prefix Tree Data Structure |
| **Day 99** | #211 | Design Add & Search Words | Medium | Trie + Wildcard Search |
| **Day 100** | #212 | Word Search II | Hard | Trie + Backtracking Matrix |

---

## 💻 Full Code Solutions for Selected LeetCode Problems (C++ & Java)

### 1. LeetCode #15: 3Sum (Two Pointers)
> 🧠 **Memory Hook:** Two friends walking towards each other from both ends of sorted array to match target sum `-nums[i]`.

#### Approach Breakdown:
- **Brute Force ($O(n^3)$):** Three nested loops checking all triplets `a + b + c == 0`.
- **Optimal Two Pointers ($O(n^2)$ Time, $O(1)$ Extra Space):** Sort array. Loop index `i` from $0$ to $n-3$. Use two pointers `left = i+1` and `right = n-1` to find pairs matching `-nums[i]`. Skip duplicate elements.

```cpp
// C++ Code - LeetCode #15 3Sum
#include <vector>
#include <algorithm>
using namespace std;

vector<vector<int>> threeSum(vector<int>& nums) {
    vector<vector<int>> res;
    sort(nums.begin(), nums.end());
    int n = nums.size();
    
    for (int i = 0; i < n - 2; ++i) {
        if (i > 0 && nums[i] == nums[i - 1]) continue; // Skip duplicate i
        int left = i + 1, right = n - 1;
        while (left < right) {
            int sum = nums[i] + nums[left] + nums[right];
            if (sum == 0) {
                res.push_back({nums[i], nums[left], nums[right]});
                while (left < right && nums[left] == nums[left + 1]) left++; // Skip duplicate left
                while (left < right && nums[right] == nums[right - 1]) right--; // Skip duplicate right
                left++; right--;
            } else if (sum < 0) left++;
            else right--;
        }
    }
    return res;
}
```

```java
// Java Code - LeetCode #15 3Sum
import java.util.*;

public class Solution3Sum {
    public List<List<Integer>> threeSum(int[] nums) {
        List<List<Integer>> res = new ArrayList<>();
        Arrays.sort(nums);
        int n = nums.length;
        
        for (int i = 0; i < n - 2; i++) {
            if (i > 0 && nums[i] == nums[i - 1]) continue;
            int left = i + 1, right = n - 1;
            while (left < right) {
                int sum = nums[i] + nums[left] + nums[right];
                if (sum == 0) {
                    res.add(Arrays.asList(nums[i], nums[left], nums[right]));
                    while (left < right && nums[left] == nums[left + 1]) left++;
                    while (left < right && nums[right] == nums[right - 1]) right--;
                    left++; right--;
                } else if (sum < 0) left++;
                else right--;
            }
        }
        return res;
    }
}
```

---

### 2. LeetCode #3: Longest Substring Without Repeating Characters (Sliding Window)
> 🧠 **Memory Hook:** Sliding window on a train—expand window right, jump left pointer forward whenever a duplicate character enters the window.

#### Approach Breakdown:
- **Brute Force ($O(n^2)$):** Check every substring for uniqueness using a Set.
- **Optimal Sliding Window ($O(n)$ Time):** Use Hash Map / Last Seen array to store last index of each character. Expand `right` pointer; if character repeated, jump `left` pointer to `last_seen[char] + 1`.

```cpp
// C++ Code - LeetCode #3
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

int lengthOfLongestSubstring(string s) {
    vector<int> last_seen(256, -1);
    int max_len = 0, left = 0;
    for (int right = 0; right < s.length(); ++right) {
        if (last_seen[s[right]] >= left) {
            left = last_seen[s[right]] + 1;
        }
        last_seen[s[right]] = right;
        max_len = max(max_len, right - left + 1);
    }
    return max_len;
}
```

```java
// Java Code - LeetCode #3
import java.util.Arrays;

public class SolutionLongestSubstring {
    public int lengthOfLongestSubstring(String s) {
        int[] lastSeen = new int[256];
        Arrays.fill(lastSeen, -1);
        int maxLen = 0, left = 0;
        for (int right = 0; right < s.length(); right++) {
            if (lastSeen[s.charAt(right)] >= left) {
                left = lastSeen[s.charAt(right)] + 1;
            }
            lastSeen[s.charAt(right)] = right;
            maxLen = Math.max(maxLen, right - left + 1);
        }
        return maxLen;
    }
}
```

---

### 3. LeetCode #739: Daily Temperatures (Monotonic Stack)
> 🧠 **Memory Hook:** Tall people in line blocking shorter people—stack holds indices in decreasing order of temperature.

#### Approach Breakdown:
- **Brute Force ($O(n^2)$):** For each day, look forward in array to find next warmer day.
- **Optimal Monotonic Decreasing Stack ($O(n)$ Time, $O(n)$ Space):** Push indices onto stack. When current temperature > temperature at top index of stack, pop index and calculate `day_diff = current_i - popped_i`.

```cpp
// C++ Code - LeetCode #739 Daily Temperatures
#include <vector>
#include <stack>
using namespace std;

vector<int> dailyTemperatures(vector<int>& temperatures) {
    int n = temperatures.size();
    vector<int> res(n, 0);
    stack<int> st; // Stores indices
    
    for (int i = 0; i < n; ++i) {
        while (!st.empty() && temperatures[st.top()] < temperatures[i]) {
            int idx = st.top();
            st.pop();
            res[idx] = i - idx;
        }
        st.push(i);
    }
    return res;
}
```

```java
// Java Code - LeetCode #739 Daily Temperatures
import java.util.Stack;

public class SolutionDailyTemperatures {
    public int[] dailyTemperatures(int[] temperatures) {
        int n = temperatures.length;
        int[] res = new int[n];
        Stack<Integer> st = new Stack<>();
        
        for (int i = 0; i < n; i++) {
            while (!st.isEmpty() && temperatures[st.peek()] < temperatures[i]) {
                int idx = st.pop();
                res[idx] = i - idx;
            }
            st.push(i);
        }
        return res;
    }
}
```

---

### 4. LeetCode #200: Number of Islands (Graph DFS / BFS)
> 🧠 **Memory Hook:** Sinking islands—when you land on `'1'`, trigger DFS to sink all connected `'1'` land cells to `'0'`.

#### Approach Breakdown:
- **Optimal Grid DFS ($O(M \times N)$ Time, $O(M \times N)$ Space):** Iterate through 2D grid. When `'1'` (land) is found, increment island count and trigger DFS to sink connected land cells (`'1'` ➔ `'0'`).

```cpp
// C++ Code - LeetCode #200 Number of Islands
#include <vector>
using namespace std;

class SolutionNumberIslands {
    void dfs(vector<vector<char>>& grid, int r, int c) {
        int rows = grid.size(), cols = grid[0].size();
        if (r < 0 || r >= rows || c < 0 || c >= cols || grid[r][c] == '0') return;
        grid[r][c] = '0'; // Sink land
        dfs(grid, r + 1, c);
        dfs(grid, r - 1, c);
        dfs(grid, r, c + 1);
        dfs(grid, r, c - 1);
    }
public:
    int numIslands(vector<vector<char>>& grid) {
        if (grid.empty()) return 0;
        int islands = 0;
        for (int r = 0; r < grid.size(); ++r) {
            for (int c = 0; c < grid[0].size(); ++c) {
                if (grid[r][c] == '1') {
                    islands++;
                    dfs(grid, r, c);
                }
            }
        }
        return islands;
    }
};
```

```java
// Java Code - LeetCode #200 Number of Islands
public class SolutionNumberIslands {
    private void dfs(char[][] grid, int r, int c) {
        int rows = grid.length, cols = grid[0].length;
        if (r < 0 || r >= rows || c < 0 || c >= cols || grid[r][c] == '0') return;
        grid[r][c] = '0';
        dfs(grid, r + 1, c);
        dfs(grid, r - 1, c);
        dfs(grid, r, c + 1);
        dfs(grid, r, c - 1);
    }

    public int numIslands(char[][] grid) {
        if (grid == null || grid.length == 0) return 0;
        int islands = 0;
        for (int r = 0; r < grid.length; r++) {
            for (int c = 0; c < grid[0].length; c++) {
                if (grid[r][c] == '1') {
                    islands++;
                    dfs(grid, r, c);
                }
            }
        }
        return islands;
    }
}
```

---

### 5. LeetCode #322: Coin Change (Dynamic Programming)
> 🧠 **Memory Hook:** Don't recount coins from scratch—remember the min coins for `amount - coin` and add $1$.

#### Approach Breakdown:
- **Optimal Bottom-Up DP ($O(\text{amount} \times \text{coins.length})$ Time):** Build 1D DP table `dp[i]` storing min coins needed for amount $i$. Transition: `dp[i] = min(dp[i], 1 + dp[i - coin])`.

```cpp
// C++ Code - LeetCode #322 Coin Change
#include <vector>
#include <algorithm>
using namespace std;

int coinChange(vector<int>& coins, int amount) {
    vector<int> dp(amount + 1, amount + 1);
    dp[0] = 0;
    for (int i = 1; i <= amount; ++i) {
        for (int coin : coins) {
            if (i - coin >= 0) {
                dp[i] = min(dp[i], 1 + dp[i - coin]);
            }
        }
    }
    return dp[amount] > amount ? -1 : dp[amount];
}
```

```java
// Java Code - LeetCode #322 Coin Change
import java.util.Arrays;

public class SolutionCoinChange {
    public int coinChange(int[] coins, int amount) {
        int[] dp = new int[amount + 1];
        Arrays.fill(dp, amount + 1);
        dp[0] = 0;
        for (int i = 1; i <= amount; i++) {
            for (int coin : coins) {
                if (i - coin >= 0) {
                    dp[i] = Math.min(dp[i], 1 + dp[i - coin]);
                }
            }
        }
        return dp[amount] > amount ? -1 : dp[amount];
    }
}
```
