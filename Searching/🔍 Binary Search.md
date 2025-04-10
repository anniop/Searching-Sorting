
---
## 📘 Problem Statement
> Given a **sorted array** of integers and a target value, return the **index** of the target value if it exists.
> Otherwise, return `-1`

---
## 🤔 Intuition
When the array is sorted, we can use a smarter approach then checking every element.
Instead of starting from the front, we can go straight to the **middle**, and then eliminate **half of the array** in every step.
This is called **divide and conquer**.

---
##  📖 Real-Life Analogy
Think of looking up a word in a dictionary:
- You don't start from the first page.
- You flip to the **middle**.
- If the word is after that page -> go right
- If before -> go left
Repeat until found or the section is empty.

This is How Binary Search Works!

---
## ✅ Approach
1. Set two pointers:
	- `low = 0`
	- `high = n -1`
2. While `low <= high`:
	- Calculate `mid = (low + high) \ 2`
	- If `arr[mid] == target`-> return `mid`
	- If `target < arr[mid]` -> eliminate right half -> `high = mid - 1`
	- If `target > arr[mid]` -> eliminate left half -> `low = mid + 1`
3. If the loop ends, return `-1` (element not found)

---
## 🔁 Dry Run Example
### Input:
```cpp
arr = [1, 3, 5, 7, 9, 11], target = 9
```

| Step | low | high | mid | arr[mid] | Comparison    | Action             |
| ---- | --- | ---- | --- | -------- | ------------- | ------------------ |
| 1    | 0   | 5    | 2   | 5        | 9 > 5         | low = mid + 1 -> 3 |
| 2    | 3   | 5    | 4   | 9        | ✅ Match found | return 4           |

---
## 🧪 Time and Space Complexity

| Case         | Time Complexity | Space Complexity |
| ------------ | --------------- | ---------------- |
| Best Case    | O(1)            | O(1)             |
| Worst Case   | O(log n)        | O(1)             |
| Average Case | O(n log n)      | O(1)             |
✅ Efficient even for large arrays

---
## ⚠️ Requirements
- ✅ The array **must be sorted**
- ❌ Does not work correctly on **unsorted** arrays

---
## 🔧 Code (C++)
```cpp
int binarySearch(vector<int>& arr, int target){
	int low = 0;
	int high = arr.size() - 1;

	while(low <= high){
		int mid = (low + high) / 2;

		if(arr[mid] == target){
			return mid;
		} else if(target < arr[mid]){
			high = mid - 1;
		} else {
			low = mid + 1;
		}
	}
	return -1;
}
```

---
## 📌 When to Use Binary Search
- ✅ When the array is sorted
-  ✅ When time is critical(logarithmic time is fast!)
- ❌ Not for unsorted data.

---
## 🔀 Variants Asked in Interviews
- Find **first** or **last** occurrence of a value.
- Return boolean (is target present?)
- Search in a **rotated sorted array**
- Binary search on **2D matrix**
- Use binary search to find:
	- Min/Max value satisfying a condition
	- Square root / peak element / element closest to target

---
## 🧠 Interview Tip
> If someone says "array is sorted", 95% of the time they expect to use **binary search**.
> It's not just for finding values, it's a **technique** used to solve many problems efficiently.