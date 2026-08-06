# 💡 Module 28: Top LeetCode & DSA Coding Interview Patterns

Quick-reference cheatsheet for the top 6 algorithmic coding patterns asked in technical interviews at MAANG / FAANG companies.

---

## ⚡ 1. Two Pointers Pattern
Used for searching pairs in sorted arrays or reversing sequences in $O(n)$ time and $O(1)$ space.

```python
# Target Sum in Sorted Array Example
left, right = 0, len(nums) - 1
while left < right:
    current_sum = nums[left] + nums[right]
    if current_sum == target:
        return [left, right]
    elif current_sum < target:
        left += 1
    else:
        right -= 1
```

---

## 🪟 2. Sliding Window Pattern
Used for subarray or substring problems (e.g., maximum sum subarray of size $K$, longest substring without repeating characters).

```python
# Fixed Size Window Example
window_sum = sum(nums[:k])
max_sum = window_sum
for i in range(k, len(nums)):
    window_sum += nums[i] - nums[i - k]
    max_sum = max(max_sum, window_sum)
```

---

## 🐢 3. Fast & Slow Pointers (Floyd's Cycle Detection)
Used to detect cycles in Linked Lists or find the middle node in $O(n)$ time and $O(1)$ space.

```python
# Linked List Cycle Detection
slow = fast = head
while fast and fast.next:
    slow = slow.next
    fast = fast.next.next
    if slow == fast:
        return True  # Cycle detected!
return False
```

---

## 📚 4. Monotonic Stack Pattern
Used to find Next Greater Element or Next Smaller Element in $O(n)$ time.

```python
# Next Greater Element
stack = []
res = [-1] * len(nums)
for i in range(len(nums)):
    while stack and nums[stack[-1]] < nums[i]:
        idx = stack.pop()
        res[idx] = nums[i]
    stack.append(i)
```
