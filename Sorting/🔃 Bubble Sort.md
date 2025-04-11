---

---

---
## 📘 Problem Statement
> Given an array of integers, sort the array in **ascending** or **descending** order using **Bubble Sort**.

---
## 🤔 Intuition
Bubble Sort is called so because larger elements **"bubble up" to the end** of the array, just like bubbles rise to the surface of water.

In each pass:
- We compare adjacent elements.
- If they are in the **wrong order**, we **swap** them.
- The largest unsorted element settles at its correct position after every pass.

We repeat this process until the array is sorted.

---
## 💡 Real-Life Analogy
Imagine lining up kids by height:
- You go one by one comparing two at a time.
- If the one on the left is taller than the one on the right, you swap them
- After one full pass, the tallest kid is at the end
- Repeat this process for the remaining kids.

---

## 📦 Dry Run Example
### Input:
```cpp
arr = [5, 3, 8, 4, 2]
```
### Pass-by-Pass breakdown:
| Pass |        Array        | Swap? |
| :--: | :-----------------: | :---: |
|  1   | [**3, 5**, 8, 4, 2] |   ✅   |
|      |   [3, 5, 8, 4, 2]   |   ❌   |
|      | [3, 5, **4, 8**, 2] |   ✅   |
|      | [3, 5, 4, **2, 8**] |   ✅   |
|  2   | [3, **5, 4**, 2, 8] |   ✅   |
|      | [3, 4, **2, 5**, 8] |   ✅   |
|  3   | [**3, 4**, 2, 5, 8] |   ❌   |
|      | [3, **2, 4**, 5, 8] |   ✅   |
|  4   | [**2, 3**, 4, 5, 8] |   ✅   |
✅ Sorted!

---
## 🧾 Code (Ascending Order)
```cpp
void bubbleSortAscending(vector<int>& arr){
	int n = arr.size();

	for(int i = 0;i < n - 1;i++){
		for(int j = 0;j < n - i - 1;j++){
			if(arr[j] > arr[j + 1]){
				swap(arr[j], arr[j + 1]);
			}
		}
	}
}
```

---
## 🔄 Code (Descending Order)
```cpp
void bubbleSortDescending(vector<int>& arr){
	int n = arr.size();

	for(int i = 0;i < n - 1;i++){
		for(int j = 0;j < n - i - 1;j++){
			if(arr[j] < arr[j + 1]){
				swap(arr[j], arr[j + 1]);
			}
		}
	}
}
```

---
## 💡 Optimization (Early Exit)
If during one pass no swaps are made -> array is already sorted
```cpp
void optimizedBubbleSort(vector<int>& arr){
	int n = arr.size();

	for(int i = 0;i < n - 1;i++){
		bool swapped = false;
		for(int j = 0;j < n - i - 1; j++){
			if(arr[j] > arr[j + 1]){
				swap(arr[j], arr[j + 1]);
				swapped = true;
			}
		}
		if(!swapped) break;  // No swaps = sorted!
	}
}
```

---
## 🧠 Why Use `n - i - 1` in the Inner Loop?
Each pass places the next largest value at the end:
- So there's **no need to compare the last `i` elements** again.
- We avoid going out of bounds(`arr[j + 1]`).
- It saves unnecessary comparisons.

---
## ⏱ Time & Space Complexity

| Case       | Time Complexity | Why                               |
| ---------- | --------------- | --------------------------------- |
| Best Case  | O(n)            | Already sorted(with optimization) |
| Average    | O($n^2$)        | All pairs need to be compared     |
| Worst Case | O($n^2$)        | Completely reverse sorted         |
| Space      | O(1)            | In-place sorting                  |

---
## ✅ When to Use
- When simplicity is more important than performance.
- For teaching sorting basics.
- For small datasets.

---
## ⚠️ When Not to Use
- On large datasets(due to O($n^2$) time)
- When stability or efficiency is critical

---
##  🧠 Interview Insights
- Rarely used in production
- Great warm-up question
- Good stepping stone to understand Insertion, Selection, and Merge sort

---
