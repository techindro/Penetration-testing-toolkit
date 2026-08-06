# ⚡ Module 23: Data Structures & Algorithms (DSA) Big-O & Complexity Cheatsheet

Complete reference for Big-O Time & Space Complexity formulas, sorting algorithms, and data structure operations required for technical coding interviews and CSE coursework.

---

## 📊 1. Data Structure Operations Time & Space Complexity

| Data Structure | Access | Search | Insertion | Deletion | Space Complexity |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Array** | $O(1)$ | $O(n)$ | $O(n)$ | $O(n)$ | $O(n)$ |
| **Linked List** | $O(n)$ | $O(n)$ | $O(1)$ | $O(1)$ | $O(n)$ |
| **Stack** | $O(n)$ | $O(n)$ | $O(1)$ | $O(1)$ | $O(n)$ |
| **Queue** | $O(n)$ | $O(n)$ | $O(1)$ | $O(1)$ | $O(n)$ |
| **Hash Table** | $N/A$ | $O(1)$ | $O(1)$ | $O(1)$ | $O(n)$ |
| **Binary Search Tree (Balanced)** | $O(\log n)$ | $O(\log n)$ | $O(\log n)$ | $O(\log n)$ | $O(n)$ |
| **Binary Search Tree (Worst)** | $O(n)$ | $O(n)$ | $O(n)$ | $O(n)$ | $O(n)$ |
| **Heap (Priority Queue)** | $O(1)$ (find-max) | $O(n)$ | $O(\log n)$ | $O(\log n)$ | $O(n)$ |

---

## ⚡ 2. Sorting Algorithms Time & Space Complexity

| Algorithm | Best Time | Average Time | Worst Time | Space Complexity | Stable? |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **QuickSort** | $O(n \log n)$ | $O(n \log n)$ | $O(n^2)$ | $O(\log n)$ | No |
| **MergeSort** | $O(n \log n)$ | $O(n \log n)$ | $O(n \log n)$ | $O(n)$ | Yes |
| **HeapSort** | $O(n \log n)$ | $O(n \log n)$ | $O(n \log n)$ | $O(1)$ | No |
| **BubbleSort** | $O(n)$ | $O(n^2)$ | $O(n^2)$ | $O(1)$ | Yes |
| **Binary Search** | $O(1)$ | $O(\log n)$ | $O(\log n)$ | $O(1)$ | N/A |

---

## 💡 3. Common Big-O Time Growth Hierarchy (Fastest to Slowest)

$$O(1) < O(\log n) < O(n) < O(n \log n) < O(n^2) < O(2^n) < O(n!)$$
