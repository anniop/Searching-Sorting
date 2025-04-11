
Welcome to the world of **sorting algorithms**, a core part of every placement and technical interview journey.

In this section, you'll learn how different sorting techniques work, when to use them, and how to explain them like a pro.

---

## 🤔 What is Sorting?

**Sorting** means arranging data in a particular order — most commonly in:
- **Ascending order** (1, 2, 3, …)
- **Descending order** (9, 8, 7, …)

---

## 🧠 Why Is Sorting Important?

- Makes **searching faster** (binary search only works on sorted data)
- Helps in **data analysis**, **ranking**, and **optimization**
- Forms the foundation of many **real-world problems**

---

## 📘 Real-Life Examples

| Example                                     | Sorting Done By     |
|--------------------------------------------|----------------------|
| E-commerce product list                    | Price (Low to High)  |
| Leaderboard in a game                      | Score (High to Low)  |
| Sorting files in your system               | Date Modified        |
| Arranging students by marks                | Total Score          |

---

## 🧪 What Will You Learn?

We'll cover every commonly asked sorting technique — both simple and advanced:

### 🟢 Beginner-Level (Easy to Visualize)

| Algorithm       | Key Idea                              |
|----------------|----------------------------------------|
| Bubble Sort     | Repeatedly swap adjacent elements      |
| Selection Sort  | Select min/max and place in right spot |
| Insertion Sort  | Insert elements into their sorted position |

---

### 🔵 Intermediate (Efficient and Used in Real Life)

| Algorithm       | Key Idea                               |
|----------------|-----------------------------------------|
| Merge Sort      | Divide array and merge sorted halves    |
| Quick Sort      | Choose pivot and partition the array    |

---

### 🔴 Advanced (For Special Cases)

| Algorithm       | Key Idea                                |
|----------------|------------------------------------------|
| Count Sort      | Use frequency/count array                |
| Radix Sort      | Sort numbers digit by digit              |
| Heap Sort       | Use max-heap/min-heap to sort            |

---

## 📊 Time & Space Complexity Table

| Algorithm       | Best     | Average     | Worst     | Space | Stable? |
|----------------|----------|-------------|-----------|--------|---------|
| Bubble Sort     | O(n)     | O(n²)       | O(n²)     | O(1)  | ✅      |
| Selection Sort  | O(n²)    | O(n²)       | O(n²)     | O(1)  | ❌      |
| Insertion Sort  | O(n)     | O(n²)       | O(n²)     | O(1)  | ✅      |
| Merge Sort      | O(n log n)| O(n log n) | O(n log n)| O(n)  | ✅      |
| Quick Sort      | O(n log n)| O(n log n) | O(n²)     | O(log n)| ❌   |
| Count Sort      | O(n+k)   | O(n+k)      | O(n+k)    | O(n+k)| ✅      |
| Radix Sort      | O(nk)    | O(nk)       | O(nk)     | O(n+k)| ✅      |
| Heap Sort       | O(n log n)| O(n log n) | O(n log n)| O(1)  | ❌      |

> 📌 k = range of input values

---

## 🧠 How to Choose the Right Sorting Algorithm?

| Scenario                                      | Best Choice          | Why                                 |
|----------------------------------------------|----------------------|--------------------------------------|
| Simple small dataset                         | Insertion Sort       | Easy to implement                    |
| Fastest for large input (in practice)        | Quick Sort           | In-place and efficient               |
| Stable and guaranteed performance            | Merge Sort           | Predictable O(n log n)               |
| Sorting when range of values is small        | Count Sort           | O(n + k) time                        |
| You need to build a priority queue           | Heap Sort            | Uses heap data structure             |

---

> 🎯 Goal: Understand the **intuition**, **dry run**, and **code** of each algorithm so you can crack interview problems confidently.

---

> 🔽 Start with: [`Bubble Sort`](Bubble Sort.md) 