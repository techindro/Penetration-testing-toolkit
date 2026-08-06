# 💡 Module 28: Top LeetCode & DSA Coding Interview Patterns (C++ STL)

Quick-reference cheatsheet for the top 6 algorithmic coding patterns using C++ Standard Template Library (STL) asked in technical interviews at MAANG / FAANG companies.

---

## ⚡ 1. Two Pointers Pattern (C++)
Used for searching pairs in sorted arrays or reversing sequences in $O(n)$ time and $O(1)$ space.

```cpp
// Target Sum in Sorted Array Example (C++)
#include <vector>
using namespace std;

vector<int> twoSum(vector<int>& nums, int target) {
    int left = 0, right = nums.size() - 1;
    while (left < right) {
        int current_sum = nums[left] + nums[right];
        if (current_sum == target) {
            return {left, right};
        } else if (current_sum < target) {
            left++;
        } else {
            right--;
        }
    }
    return {};
}
```

---

## 🪟 2. Sliding Window Pattern (C++)
Used for subarray or substring problems (e.g., maximum sum subarray of size $K$, longest substring without repeating characters).

```cpp
// Fixed Size Window Example (C++)
#include <vector>
#include <numeric>
#include <algorithm>
using namespace std;

int maxSumSubarray(const vector<int>& nums, int k) {
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

---

## 🐢 3. Fast & Slow Pointers (Floyd's Cycle Detection) (C++)
Used to detect cycles in Linked Lists or find the middle node in $O(n)$ time and $O(1)$ space.

```cpp
// Linked List Cycle Detection (C++)
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
        if (slow == fast) return true; // Cycle detected!
    }
    return false;
}
```

---

## 📚 4. Monotonic Stack Pattern (C++)
Used to find Next Greater Element or Next Smaller Element in $O(n)$ time using `std::stack`.

```cpp
// Next Greater Element (C++)
#include <vector>
#include <stack>
using namespace std;

vector<int> nextGreaterElement(const vector<int>& nums) {
    int n = nums.size();
    vector<int> res(n, -1);
    stack<int> st; // Monotonic decreasing stack
    
    for (int i = 0; i < n; ++i) {
        while (!st.empty() && nums[st.top()] < nums[i]) {
            int idx = st.top();
            st.pop();
            res[idx] = nums[i];
        }
        st.push(i);
    }
    return res;
}
```
