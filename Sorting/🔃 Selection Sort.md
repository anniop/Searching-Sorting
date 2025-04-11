---

---

---
## 📘 Problem Statement
> Given an array of integers, sort the array in **ascending** or **descending** order using the **Selection Sort** algorithm.

---
## 🤔 Intuition
Selection Sort works by **dividing the array into two parts**:
- A **sorted part** (which grows from left to right)
- An **unsorted part** (which shrinks from right to left)

In every pass:
1. You **select the minimum (or maximum)** value from the unsorted part.
2. You **swap** it with the first element of the unsorted part.
By the end, all elements are sorted one by one.

---
## 💡 Real-Life Analogy
Imagine you're picking teams in a game:
- You pick the **best available player** from the remaining pool
- Once picked, they're added to your sorted team
- Repeat until the whole team is formed

Selection Sort does exactly this with numbers.

---
## 🔁 Dry Run Example
```cpp
Input: arr[5, 3, 8, 4, 2]
```

| Pass | Unsorted        | Min | Swap With | Array After Pass |
| ---- | --------------- | --- | --------- | ---------------- |
| 1    | [5, 3, 8, 4, 2] | 2   | 5         | [2, 3, 8, 4, 5]  |
| 2    | [3, 8, 4, 5]    | 3   | 3         | [2, 3, 8, 4, 5]  |
| 3    | [8, 4, 5]       | 4   | 8         | [2, 3, 4, 8, 5]  |
| 4    | [8, 5]          | 5   | 8         | [2, 3, 4, 5, 8]  |
✅ Sorted in ascending order!

---
## 📦 Algorithm Steps
1. Loop `i`from `0` to `n - 1`
2. Assume `arr[i]` is the minimum element.
3. Loop `j` from `i + 1` to `n`
4. If `ar[j] < arr[minIndex]`, update `minIndex = j`
5. After the inner loop, swap `arr[i]` and `arr[minIndex]`

---
## 🔧 C++ Code (Ascending Order)
```cpp
void selectionSort(vector<int>& arr){
	int n = arr.size();

	for(int i = 0;i < n - 1;i++){
		int minIndex = i;

		for(int j = i + 1;j < n;j++){
			if(arr[j] < arr[minIndex]) {
				minIndex = j;
			}
		}
		swap(arr[i], arr[minIndex]);
	}
}
```

---
## 🔄 C++ Code (Descending Order)

```cpp
void selectionSortDescending(vector<int>& arr) {
    int n = arr.size();

    for (int i = 0; i < n - 1; i++) {
        int maxIndex = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] > arr[maxIndex]) {
                maxIndex = j;
            }
        }
        swap(arr[i], arr[maxIndex]);
    }
}

```

---
## ⏱ Time and Space Complexity
|Case|Time Complexity|Why|
|---|---|---|
|Best|O(n²)|Still needs to check all elements|
|Average|O(n²)|Nested loop always runs|
|Worst|O(n²)|Same as average|
|Space|O(1)|In-place, no extra memory used|
|Stable|❌ (Not stable by default)|

---
## ✅ When to Use
- When the size of the array is **very small**
- When **simplicity** is more important than performance
- When **swapping fewer times** is desirable(compared to Bubble sort)

---
## ⚠️ When Not to Use
- For large datasets it's **too slow**.
- When stability is required (e.g., sorting by multiple keys)

---
## 📌 Interview Tips
- Great for explaining the basic idea of sorting.
- Used more for **educational** and **conceptual** purposes.
- Understand it well to transition into **more optimized algorithm** like Merge Sort and Quick Sort.