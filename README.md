# 📚 Data Structures & Algorithms (DSA) Revision

> A hands-on, production-grade revision toolkit implementing foundational **Linear Data Structures**, **Non-Linear Data Structures**, and **Sorting Algorithms** from scratch in Python.

---

## 🗂️ Table of Contents

- [Overview](#-overview)
- [Notebook Breakdown](#-notebook-breakdown)
  - [1. Linear Data Structures (`Linear_Data_Structures.ipynb`)](#1-linear-data-structures-linear_data_structuresipynb)
  - [2. Non-Linear Data Structures (`Non_Linear_data_Structures.ipynb`)](#2-non-linear-data-structures-non_linear_data_structuresipynb)
  - [3. Sorting Algorithms (`Sorting.ipynb`)](#3-sorting-algorithms-sortingipynb)
- [⚡ Master Complexity Cheat Sheet](#-master-complexity-cheat-sheet)
  - [Data Structures Complexity](#data-structures-complexity)
  - [Sorting Algorithms Complexity](#sorting-algorithms-complexity)
- [💡 Key Python Engineering Gotchas](#-key-python-engineering-gotchas)
- [🚀 How to Run](#-how-to-run)

---

## 📖 Overview

This repository section serves as a fast-reference, conceptual refresher, and coding interview preparation guide. Each notebook contains:
- **Clean Object-Oriented Implementations**: Classes written with readable methods.
- **ASCII & Visual Diagrams**: Clear representations of trees, linked nodes, stacks, and graphs.
- **Recursive vs. Iterative Dual Solutions**: Showing both approaches and explaining real-world trade-offs.
- **Big-O Analysis**: Time and space complexities broken down per operation.

---

## 🔍 Notebook Breakdown

### 1. Linear Data Structures ([`Linear_Data_Structures.ipynb`](./Linear_Data_Structures.ipynb))
Covers sequential data structures where each element has a distinct predecessor and successor:

- **Dynamic Arrays**:
  - Contiguous memory allocation.
  - $O(1)$ instant index-based lookup.
  - $O(N)$ insertion/deletion overhead due to element shifting.
- **Singly Linked List**:
  - Node-based pointer chain (`val` $\to$ `next`).
  - $O(1)$ insertion/deletion at the head.
  - Overcomes array capacity limits without contiguous memory requirements.
- **Stack (LIFO)**:
  - Last-In, First-Out access via `push`, `pop`, and `peek`.
  - Implemented cleanly using `collections.deque`.
  - Essential for function call stacks, backtracking, and parenthesis matching.
- **Queue (FIFO)**:
  - First-In, First-Out access via `enqueue` and `dequeue`.
  - Implemented via `collections.deque.popleft()` ($O(1)$) to avoid the $O(N)$ penalty of `list.pop(0)`.
  - Essential for task scheduling, buffering, and Breadth-First Search.
- **Hash Map**:
  - Key-Value store mapped via a hashing function.
  - Near-$O(1)$ average lookups and mutations.
  - Collision resolution mechanisms: Separate Chaining vs. Open Addressing.

---

### 2. Non-Linear Data Structures ([`Non_Linear_data_Structures.ipynb`](./Non_Linear_data_Structures.ipynb))
Covers hierarchical and networked data structures:

- **General Trees (N-ary Tree)**:
  - Multi-child hierarchy with parent pointers.
  - Methods: `add_child`, `get_level` (depth calculation), and recursive hierarchical indentation printing.
- **Binary Search Tree (BST)**:
  - Maintains the BST invariant: $\text{Left} < \text{Root} < \text{Right}$.
  - Custom visual tree branch renderer (`├──`, `└──`).
  - Operations:
    - **Insert**: Traverses down to leaf position ($O(\log N)$ avg).
    - **Search**: Binary elimination of subtrees ($O(\log N)$ avg).
    - **Delete**: Handles all **3 distinct deletion cases**:
      1. *Leaf Node*: Removed immediately.
      2. *Single Child*: Replaced by its child.
      3. *Two Children*: Swapped with its **In-Order Successor** (minimum value in right subtree) and recursively cleaned up.
- **Tree Traversals (Recursive vs. Iterative)**:
  - **In-Order** ($\text{Left} \to \text{Root} \to \text{Right}$): Produces sorted order for BSTs.
  - **Pre-Order** ($\text{Root} \to \text{Left} \to \text{Right}$): Used for tree cloning and serialization.
  - **Post-Order** ($\text{Left} \to \text{Right} \to \text{Root}$): Used for bottom-up cleanup / node deletion.
  - **Level-Order (BFS)**: Iterative traversal via `collections.deque`.
  - **Iterative DFS**: Uses an explicit `stack` to prevent recursion depth limit errors on large/skewed trees.
- **Graphs (Adjacency List)**:
  - Vertices and Edges represented as an adjacency list ($O(V + E)$ memory).
  - **Breadth-First Search (BFS)**: Explores layer-by-layer; finds shortest paths in unweighted graphs.
  - **Depth-First Search (DFS)**: Implemented both recursively and iteratively via a stack; essential for cycle detection and path existence.
  - Cycle prevention using a `visited` array/set.

---

### 3. Sorting Algorithms ([`Sorting.ipynb`](./Sorting.ipynb))
Covers fundamental comparison-based and non-comparison sorting techniques:

- **Bubble Sort**: Iteratively bubbles the largest element to the end ($O(N^2)$).
- **Selection Sort**: Finds the minimum element from the unsorted sub-array and swaps it into place ($O(N^2)$).
- **Insertion Sort**: Inserts elements into their correct position in the sorted prefix ($O(N)$ best case, $O(N^2)$ worst case).
- **Merge Sort**: Divide-and-conquer algorithm with guaranteed $O(N \log N)$ time and $O(N)$ auxiliary space (Stable).
- **Quick Sort**: Divide-and-conquer algorithm with in-place partitioning around a pivot ($O(N \log N)$ average).
- **Heap Sort**: Priority-based sorting using a binary heap structure ($O(N \log N)$ guaranteed, in-place).

---

## ⚡ Master Complexity Cheat Sheet

### Data Structures Complexity

| Data Structure | Access | Search | Insertion | Deletion | Space Complexity |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Array** | $O(1)$ | $O(N)$ | $O(N)$ | $O(N)$ | $O(N)$ |
| **Singly Linked List** | $O(N)$ | $O(N)$ | $O(1)$ (head) | $O(1)$ (head) | $O(N)$ |
| **Stack (deque)** | $O(N)$ | $O(N)$ | $O(1)$ (top) | $O(1)$ (top) | $O(N)$ |
| **Queue (deque)** | $O(N)$ | $O(N)$ | $O(1)$ (rear) | $O(1)$ (front) | $O(N)$ |
| **Hash Map** | $O(1)$ avg | $O(1)$ avg | $O(1)$ avg | $O(1)$ avg | $O(N)$ |
| **Binary Search Tree** | $O(\log N)$ avg | $O(\log N)$ avg | $O(\log N)$ avg | $O(\log N)$ avg | $O(N)$ |
| **Graph (Adjacency List)** | — | $O(V + E)$ | $O(1)$ (edge add) | $O(E)$ | $O(V + E)$ |

---

### Sorting Algorithms Complexity

| Algorithm | Best Time | Average Time | Worst Time | Space | Stable? | In-Place? |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Bubble Sort** | $O(N)$ | $O(N^2)$ | $O(N^2)$ | $O(1)$ | Yes | Yes |
| **Selection Sort**| $O(N^2)$ | $O(N^2)$ | $O(N^2)$ | $O(1)$ | No | Yes |
| **Insertion Sort**| $O(N)$ | $O(N^2)$ | $O(N^2)$ | $O(1)$ | Yes | Yes |
| **Merge Sort** | $O(N \log N)$ | $O(N \log N)$ | $O(N \log N)$ | $O(N)$ | Yes | No |
| **Quick Sort** | $O(N \log N)$ | $O(N \log N)$ | $O(N^2)$ | $O(\log N)$ | No | Yes |
| **Heap Sort** | $O(N \log N)$ | $O(N \log N)$ | $O(N \log N)$ | $O(1)$ | No | Yes |

---

## 💡 Key Python Engineering Gotchas

1. **Avoid `list.pop(0)` for Queues**:
   Standard Python `list.pop(0)` is $O(N)$ because every remaining element must shift left. Always prefer `collections.deque.popleft()`, which runs in strictly $O(1)$ time.
2. **Recursion vs. Iteration on Trees/Graphs**:
   Python's default recursion limit is $1000$ (`sys.getrecursionlimit()`). For deeply skewed trees or large graphs, recursive DFS can trigger a `RecursionError`. Using an explicit stack (`list`) or queue (`deque`) provides safety against stack overflow.
3. **Graph Cycle Prevention**:
   Always mark nodes in your `visited` set / boolean array **at the time of enqueueing / visiting** to avoid pushing redundant duplicate nodes into memory.

---

## 🚀 How to Run

1. Open this workspace in **VS Code** or **JupyterLab**.
2. Select any notebook:
   - [`Linear_Data_Structures.ipynb`](./Linear_Data_Structures.ipynb)
   - [`Non_Linear_data_Structures.ipynb`](./Non_Linear_data_Structures.ipynb)
   - [`Sorting.ipynb`](./Sorting.ipynb)
3. Ensure your Python 3 environment kernel is selected.
4. Execute individual cells using `Shift + Enter` to test the implementations and view the visual outputs.
