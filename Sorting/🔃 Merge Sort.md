## 📘 Problem Statement
> You are given an array of integers, Sort it in ascending order using the **Merge Sort** algorithm.

---
## 🤔 What is Merge Sort?
**Merge Sort** is a **Divide and Conquer Algorithm**, which means:
1. You **divide** the array into smaller parts.
2. **Sort** each part
3. Then **merge** them back into a sorted array.
It works recursively each part is split until we reach size 1 (which is already sorted), and then we combine.
---
## 💡 Intuition
Instead of sorting the entire array at once, we make the problem easier by breaking it into **smaller sub-problems** (sorting small parts), and then we **combine** them.
This idea is useful when sorting large arrays efficiently it guarantees a consistent performance of `O(n log n)`.

---
## 📚 Real-Life Analogy
> Suppose you're sorting exam papers:
- You divide them into 2 piles
- Continue dividing each pile until each has 1 paper
- Then compare and combine piles in sorted order
Eventually, all piles merge into a single **sorted stack**.
---
## Code in CPP
```cpp
void merge(vector<int>& arr, int start, int mid, int end){
	vector<int> temp;
	int i = start;
	int j = mid + 1;
	while(i <= mid && j <= end) {
		if(arr[i] <= arr[j]){
			temp.push_back(arr[i]);
			i++;
		} else {
			temp.push_back(arr[j]);
			j++;
		}
	}

	while(i <= mid){
		temp.push_back(arr[i]);
		i++;
	}

	while(j <= end){
		temp.push_back(arr[j]);
		j++;
	}

	for(int i = 0; i < temp.size();i++){
		arr[i + start] = temp[i];
	}
}

void mergeSort(vector<int>& arr, int start, int end){
	if(start < end){
		int mid = start + (end - start) / 2;

		mergeSort(arr, start, mid);  // Sort left half
		mergeSort(arr, mid + 1, end); // Sort right half
		merge(arr, start, mid, end); // Merge both halves
	}
}
```
---
### `merge()` Function (Handles the merging of two sorted halves)
```cpp
void merge(vector<int>& arr, int start, int mid, int end);
```
- Takes:
	- `arr`: The full array
	- `start`: Starting index of the first half
	- `mid`: End index of the first half
	- `end`: End index of the second half

> 🔀 Example: `arr = [5, 3, 8, 4, 2]`
> When merging `start = 0`, `mid = 1`, `end = 2`
> We're merging: `arr[0...1]` and `arr[2...2]`
---
```cpp
vector<int> temp;
```
- Temporary array to hold the merged result.
- Avoids overwriting `arr` while merging
---
```cpp
int i = start;
int j = mid + 1;
```
- Two pointers:
	- `i` for the **left subarray(`start to mid`)**.
	- `j` for the **right subarray(`mid + 1 to end`)**
---
### 🔁 Merge the Two Sorted Subarrays
```cpp
while(i <= mid && j <= end){
	if(arr[i] <= arr[j]){
		temp.push_back(arr[i]);
		i++
	} else {
		temp.push_back(arr[j]);
		j++;
	}
}
```
- Compares elements from both halves.
- Pushes the **smaller one** into `temp`
- Increments the pointer of the element used
- Continues until one of the two halves is fully traversed
---
### 🧹 Copy Remaining Elements (One side might still have values)
```cpp
while(i <= mid){
	temp.push_back(arr[i]);
	i++;
}

while(j <= end){
	temp.push_back(arr[j]);
	j++;
}
```
- After the main loop, if **left half** still has values (`i <= mid`), copy them
- If **right half** still has values (`j <= end`), copy them
- This ensures all elements are included.
---
### 🔁 Copy Sorted Values Back into Original Array
```cpp
for(int i = 0;i < temp.size();i++){
	arr[i + start] = temp[i];
}
```
- `temp` now has the sorted version of the portion `arr[start...end]`.
- Copy `temp` back into the corresponding part of `arr`
- `i + start`: Maintains correct offset in original array.
---
## `mergeSort()` Function (Handles recursive divide)
```cpp
void mergeSort(vector<int>& arr, int start, int end){
	if(start < end){
		int mid = start + (end - start) / 2;

		mergeSort(arr, start, mid); // Sort the left half
		mergeSort(arr, mid + 1, end); // Sort the right half
		merge(arr, start, mid, end); // Merge the two sorted halves
	}
}
```
- **Base case**: If there's one or zero elements, it's already sorted.
- **Mid Point**: Split array into two halves
	- This avoids overflow compared to `(start + end) / 2`
- Recursively splits the array into halves
- Merges the sorted halves as recursion unwinds
- **Recursion depth is log(n)**, and at each level we merge **n elements**, giving time complexity **O(n log n)**
---
## ✅ Final Output
```cpp
Sorted Array : 2 3 4 5 8
```
---
## 🧠 Summary of Concepts in Code

| Concept            | Used In                        |
| ------------------ | ------------------------------ |
| Recursion          | `mergeSort()`                  |
| Two-Pointer method | `merge()`                      |
| Extra space        | Temporary vector `temp`        |
| Divide & Conquer   | Whole strategy of Merge Sort   |
| Stable Sort        | ✅ Yes, maintains element order |

---
## 📈 Time and Space Complexity
| Case    | Time Complexity | Why                                |
| ------- | --------------- | ---------------------------------- |
| Best    | O(n log n)      | Recursive divide + merge           |
| Average | O(n log n)      | Works the same regardless of order |
| Worst   | O(n log n)      | Even reverse-sorted input          |
| Space   | O(n)            | Due to temporary arrays            |
| Stable  | ✅ Yes           | Maintains order of equal elements  |

---
## ✅ When to Use Merge Sort
- When **guaranteed O(n log n)** time is needed
- When **stability** is important(e.g., multi-level sorting)
- For **linked lists** (can be made in-place)
---
## ⚠️ When Not to Use Merge Sort
- Space is a constraint (it uses extra space)
- Simpler algorithms work better for very small arrays
---
## 📌 Summary
- **Merge Sort** is a powerful and consistent sorting algorithm
- It uses **Divide and Conquer** to break down the problem
- Always performs in **O(n log n)**
- It's **stable**, but not in-place
- Excellent for interviews.