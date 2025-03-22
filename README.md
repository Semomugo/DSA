# DSA
# Q1.md

## Big O Notation.

Under Big O notation we describe the highest possible efficiency of time and space consumption that an algorithm exhibits based on input data scale increases. It focuses on the largest term and ignores constants and lower-order terms.

**1. Constant Rule;0(1)**

   - If the algorithm's runtime complexity remains constant regardless of the input size.0(1).
   - **Example:** Accessing an element in an array by the index.
     ```java
     int[] arr = {1, 2, 3, 4, 5};
     int element = arr[0]; // Accessing the first element
     ```
     This takes the same amount of time regardless of how large the array is.

**2. Dominant Term Rule; O(n), O(n^2), O(log n).**

   - This is when an algorithm's runtime is determined by multiple terms and the dominant term is considered.
   - **Example:**
     ```java
     for (int i = 0; i < n; i++) { // O(n)
         // Some operations
     }
     for (int j = 0; j < n; j++) { // O(n)
         // Some operations
     }
     ```
     If an algorithm has two loops that iterate `n` times, the combined runtime is O(n + n), which is O(2n). However the dominant term rule, we drop the constant 2 and represent it as O(n).

   - **Example (Quadratic):**
     ```java
     for (int i = 0; i < n; i++) {
         for (int j = 0; j < n; j++) {
             // Some operations
         }
     }
     ```
     This nested loop has a runtime of O(n * n), which is O(n^2).

   - **Example (Logarithmic):**
     ```java
     for (int i = 1; i < n; i = i * 2) {
         // Some operations
     }
     ```
     This loop splits the search space in each iteration, resulting in a runtime of O(log n).

**3. Sum Rule; O(a + b)**

   - If an algorithm performs two independent operations their complexities are added.
   - **Example:**
     ```java
     for (int i = 0; i < n; i++) { // O(n)
         // Some operations
     }
     for (int j = 0; j < m; j++) { // O(m)
         // Some operations
     }
     ```
     The combined runtime is O(n + m). If n and m are related, it simplifies. If m is much smaller than n, it will be O(n).

**4. Product Rule; O(a * b)**

   - If an algorithm performs operations their complexities are multiplied.
   - **Example:**
     ```java
     for (int i = 0; i < n; i++) { // O(n)
         for (int j = 0; j < m; j++) { // O(m)
             // Some operations
         }
     }
     ```
     The combined runtime is O(n * m). If n and m are equal, it simplifies to O(n^2).

**5. Ignoring Constants.**

   - These are factors ignored in Big O notation.
   - **Example:** O(2n), O(100), and O(n/2) are simplified to O(n), O(1), and O(n).

**6. Ignoring Lower-Order Terms:**

   - These are Lower-order terms ignored when determining the dominant term.
   - **Example:** O(n^2 + n) is simplified to O(n^2) because n^2 grows faster than n as n approaches infinity.

**# Q2.md**

## Arrays VS linked lists

Here's a comparison of arrays and linked lists in terms of memory allocation, performance, and insertion and deletion operations:

**1. Memory Allocation:**

   - **Arrays:**
     -Multiple data structures use arrays when they need a block of memory that occupies a single continuous space.
     -The array requires its dimensions known both at compile time or during its memory allocation phase.
     -The memory allocation method relies on fixed and static processes.
   - **Linked Lists:**
     - Link lists implement dynamic allocation methods for each node storage.
     - Single nodes exist independently throughout the system memory.
     - Linked lists use flexible memory allocation methods to organize their data storage.


**2. Performance:**

   - **Arrays:**
     - The process of reaching elements at specific indices requires no more than constant time O(1).
     - A search algorithm has a worst time complexity of O(n) during linear searches yet it becomes O(log n) after sorting the data.
   - **Linked Lists:**
     - The process of accessing list elements through indexing requires linear time (O(n)) since you must scan through the entire list.
     - The operation of searching for an element within the list requires linear time complexity of O(n).

**3. Insertion and Deletion Operations:**

   - **Arrays:**
     - To add or remove an element from the middle of an array the subsequent elements must be shifted creating an average runtime complexity of O(n).
     - The average complexity for inserting or deleting elements at the end of the array is O(1).
   - **Linked Lists:**
     - The operations of adding or removing nodes from the start or end of the list take constant time O(1) when you control the head or tail references.
     - The process of putting or taking out nodes from inside the list demands finding the correct spot through list traversal which results in an O(n) time complexity. You can achieve O(1) execution time by having a reference to the node before your insertion or deletion area.

**Summary Table:**

| Feature           | Arrays               | Linked Lists         |
|-------------------|----------------------|----------------------|
| Memory Allocation | Static, Contiguous   | Dynamic, Scattered   |
| Accessing Element | O(1)                 | O(n)                 |
| Searching         | O(n) or O(log n)     | O(n)                 |
| Insertion/Deletion| O(n) (middle), O(1) (end) | O(1) (head/tail), O(n) (middle) |
