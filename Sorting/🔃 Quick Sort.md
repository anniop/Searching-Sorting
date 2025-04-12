## 📘 Problem Statement

> Given an array of integers, sort it in ascending order using the **Quick Sort** algorithm.

Quick Sort is a **Divide and Conquer** algorithm that sorts the array **in-place**, unlike Merge Sort.

---
## 🤔 Intuition
- Pick a **Pivot element**(usually the last element).
- Rearrange the array so that:
	- Elements **≤ pivot** go to the left.
	- Element **> pivot** go to the right.
- Recursively sort the left and right parts.
---
## 🧠 Key Concept: Partitioning
- Rearranges elements based on the pivot:
	- Left to pivot: smaller or equal
	- Right of pivot: Larger
- Pivot is placed at its correct position
- Recurse on left and right of the pivot
---
## 💻 Code in CPP
```cpp
int partition(vector<int>& arr, int st, int end){
	int idx = st - 1;
	int pivot = arr[end];

	for(int j = st; j < end; j++){
		if(arr[j] <= pivot){
			idx++;
			swap(arr[j], arr[idx]);
		}
	}
	idx++;
	swap(arr[end], arr[idx]);
	return idx;
}

void quickSort(vector<int>& arr, int st, int end){
	if(st < end){
		int pivIdx = partition(arr, st, end);
		quickSort(arr, st, pivIdx - 1); // Left Half
		quickSort(arr, pivIdx + 1, end); // Right Half
	}
}
```
---
## 🧠 Line-by-Line Explanation
#### `partition()`
- `int idx = st - 1;`
	-> Keeps track of the boundary for smaller elements.
- `int pivot = arr[end];`
	-> Picks last element as pivot;
- `for(j = st; j < end)`
	-> Iterates over elements to compare with pivot.
- `if (arr[j] <= pivot)`
	-> Found an element that belongs on the left, so increment `idx` and swap
- `swap(arr[end], arr[idx + 1])`
	-> Place pivot in the middle of small and large sections.
- `return idx + 1;`
    -> Return the pivot's correct index.
---
#### `quickSort()`
- Base case : `if(st < end)`
- Find pivot's position using `partition()`
- Recursively sort left and right sides.
---
## 🔁 Dry Run
For Input:
`arr = [7, 2, 1, 6, 8, 5, 3, 4]`
1. Pivot = 4 -> rearranges array and places 4 at index 3
2. Sort left: [2, 1, 3]
3. Sort right: [8, 5, 7, 6]
4. Final Output: [1, 2, 3, 4, 5, 6, 7, 8]
---
## ⏱ Time & Space Complexity

| Case    | Time       | Notes                               |
| ------- | ---------- | ----------------------------------- |
| Best    | O(n log n) | Balanced partitions                 |
| Average | O(n log n) | Common case                         |
| Worst   | O($n^2$)   | Already sorted or all same elements |
| Space   | O(log n)   | Recursive stack space(in-place)     |
| Stable  | ❌ No       | Equal elements order may change     |

---
## ✅ Summary
- Divide -> Partition -> Recur
- Works well in practice (faster than merge sort due to no extra memory)
- Not stable, but space-efficient
- Must-know for interviews.:w
---
