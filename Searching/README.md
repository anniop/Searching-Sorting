Searching is one of the most basic but powerful tools in programming.  
It helps us find whether a specific value exists — and **where** it exists — in a dataset.

This section will walk you through the **most common and interview-relevant searching techniques**, starting from the simplest and going up to powerful variants.

---

## 🤔 What is Searching?

**Searching** means finding the position (index) or existence of a value inside a collection (like an array).

---

## 📘 Real-Life Examples

| Example                                   | What You’re Searching |
|------------------------------------------|------------------------|
| Looking up a contact on your phone       | Name                  |
| Finding a word in a dictionary           | Page number            |
| Checking if a number is in a lottery list| Number exists or not   |

---

## 🧠 Why Is Searching Important?

- Used in **almost every application** — from databases to file systems
- Forms the base of **decision-making logic**
- Essential for **optimization**, **AI**, and **problem-solving**
- Forms the foundation for **more advanced algorithms**

---

## 🔎 What Will You Learn?

We’ll cover these popular searching techniques:

| Level       | Algorithm         | Idea                                     |
|-------------|-------------------|------------------------------------------|
| 🔰 Basic     | Linear Search      | Go element-by-element                    |
| ⚡ Optimized | Binary Search      | Divide and conquer on sorted arrays      |
| 💡 Advanced  | First/Last Position (Binary Search variant) |
| 🔁 Bonus     | Ternary Search     | Divide into three parts (for optimization problems) |

---

## 📊 Time & Space Complexity Table

| Algorithm         | Best Case | Average Case | Worst Case | Space | Sorted Required? |
|------------------|-----------|--------------|------------|--------|------------------|
| Linear Search     | O(1)      | O(n)         | O(n)       | O(1)  | ❌ No            |
| Binary Search     | O(1)      | O(log n)     | O(log n)   | O(1)  | ✅ Yes           |
| Ternary Search    | O(1)      | O(log n)     | O(log n)   | O(1)  | ✅ Yes (unimodal function) |

---

## 🧠 When to Use Which?

| Scenario                              | Best Search Algorithm | Why                         |
|---------------------------------------|------------------------|-----------------------------|
| Small, unsorted dataset               | Linear Search          | No need for pre-processing  |
| Fast search in a sorted array         | Binary Search          | O(log n) speed              |
| Searching for optimal result in a curve| Ternary Search         | For unimodal functions      |
| Finding first or last position        | Modified Binary Search | Works with duplicate values |

---

## 🚀 Use Cases of Searching in Interviews

- **Search in rotated sorted array**
- **Peak element in mountain array**
- **Search in 2D matrix**
- **Allocate minimum pages (binary search on answers)**
- **Aggressive cows, painters partition, EKO problem (binary search on result)**

---

> 🎯 Goal: Understand **how**, **when**, and **why** to use each searching technique so you can explain and apply them with confidence during coding rounds.

---

> 🔽 Start with: [`Linear Search`](obsidian://open?vault=Obsidian%20Vault&file=Searching%20%26%20Sorting%2FSearching%2F%F0%9F%94%8D%20Linear%20Search)

