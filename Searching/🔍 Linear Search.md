---

---
---
## Problem Statement
> Given an array of `n` elements and a target value, check whether the target is present in the array.
> If present, return the **index** at which it occurs.
> If not, return `-1`.

---
## 🤔 Intuition
Linear search is the **simplest way** to find an element in a list.
It works just like a human would scan a list **one item at a time**.

---
## 💡 Real-Life Analogy
Imagine you are looking for a specific name in a name in a class attendance sheet.
You don't know if the names are in order, so you check **each one from top to bottom** until you find it.

---
## 🧠 Approach
1. Start from the first element (index 0).
2. For each element:
	- If it matches the target ->return the index.
	- Else -> move to the next element.
3. If you reach the end and haven't found the target -> return `-1`

---
## 🔁 Dry Run
### Input:
```cpp
arr = [4, 10, 3, 8, 9], target = 3
```

| Step | i(index) | arr[i] | Match with Target? | Action         |
| ---- | -------- | ------ | ------------------ | -------------- |
| 1    | 0        | 4      | No                 | Continue       |
| 2    | 1        | 10     | No                 | Continue       |
| 3    | 2        | 3      | Yes                | Retrun Index 2 |

---

## 🔧 Code in CPP
```cpp
int linearSearch(vector<int>& nums, int target){
	for(int i = 0;i < n;i++){
		if(nums[i] == target){
			return i;
		}
	}
	return -1;
}
```

---

## 🧪 Time and Space Complexity

| Case         | Time Complexity | Space Complexity |
| ------------ | --------------- | ---------------- |
| Best Case    | O(1)            | O(1)             |
| Worst Case   | O(n)            | O(1)             |
| Average Case | O(n)            | O(1)             |

---

## 🧠 When to Use Linear Search
- ✅ The array is **unsorted**
- ✅ Dataset is **small**
- ✅ You need a **quick and simple** solution
- ❌ Not preferred when performance is important or for **large datasets**.

---

## 🎯 Interview Tips
- Often used in brute-force solutions for warm-up problems.
- Used as a fallback when no better algorithm applies.
- Know how to **extend** it for variants:
	- Find first/last occurrence
	- Count number of times a target appears
	- Apply to **2D arrays**

---
## 📌 Variants Asked in Interviews
- Return index of first/last occurrence
- Check if an element exists(return bool)
- Count total occurrences
- Search in a matrix().