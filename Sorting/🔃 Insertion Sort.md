
---
## 📘 Problem Statement
> Given an array of integers, sort the array in ascending or descending order using **Insertion Sort** algorithm.

---
## 🤔 Intuition
Insertion Sort works just like **sorting playing cards** in your hand:
- You pick one card at a time from the deck.
- You **compare** it with the cards already in your hand (which are sorted)
- You **insert it** into the right position by shifting larger cards to the right

You repeat this process until all the cards are sorted.

---
## 💡 Real-Life Analogy
When people receive marksheets and line up according to increasing roll numbers:
- Each new person enters the queue.
- Looks for their correct place by comparing with others.
- Others shift to make space for the new one.

---
##  🔁 Dry Run Example
```cpp
Input: arr = [5, 3, 8, 4, 2]
```

| Step | Key | Compare With | Shift Elements         | Insert At | Resulting Array |
| ---- | --- | ------------ | ---------------------- | --------- | --------------- |
| 1    | 3   | 5            | Shift 5 to the right   | Index 0   | [3, 5, 8, 4, 2] |
| 2    | 8   | 5            | None                   | Index 2   | [3, 5, 8, 4, 2] |
| 3    | 4   | 8, 5         | Shift 8, Shift 5       | Index 1   | [3, 4, 5, 8, 2] |
| 4    | 2   | 8, 5, 4, 3   | Shift all to the right | Index 0   | [2, 3, 4, 5, 8] |
✅ Sorted in ascending order!

---
## 🔧 C++ Code (Ascending Order)

```cpp
void insertionSort(vector<int>& arr){
	int n = arr.size();

	for(int i = 1;i < n;i++){
		int key = arr[i];
		int j = i - 1;

		while(j >= 0 && arr[j] > key){
			arr[j + 1] = arr[j];
			j--;
		}

		arr[j + 1] = key;
	}
}
```

---
## 🧠 Step-by-Step Code Explanation
Let's walk through each line of the insertion sort logic in **plain, simple English**:
-  `int key = arr[i];`
	- We're picking the element at index `i` to insert it into the correct place.
	- This is like picking a new card to insert into your hand.
---
- `int j = i - 1;`
	- We're starting the comparison from the **previous element**(to the left of key).
	- We'll compare backwards to find where the `key` belongs.
---
- `while (j >= 0 && arr[j] > key`
	- As Long as:
		1. We're still inside the array
		2. And the element is **greater than the key**
- We need to **shift it one position to the right** to make space for the key.
---
- `arr[j + 1] = arr[j];`
	- This moves the larger element one place to the right.
---
- `arr[j + 1] = key;`
	- Now that all bigger elements are moved, we insert the key into the correct slot.
---
## 🔁 Dry Run with Code
Let's dry run it with:
```cpp
arr = [5, 3, 8, 4, 2]
```
**i = 1 ->key = 3**
- Compare with 5 -> shift 5 to shift
- Insert 3 at index 0
	- ⏩ `[3, 5, 8, 4, 2]`

**i = 2 -> key = 8**
- Compare with 5 -> no shift
- Place 8 where it is
	- ⏩ `[3, 5, 8, 4, 2]`

**i = 3 -> key = 4**
- Compare with 8 -> shift
- Compare with 5 -> shift
- Place 4 at index 1
	- ⏩ `[3, 4, 5, 8, 2]`
**i = 4 -> key = 2
- Compare with 8, 5, 4, 3 -> shift all
- Place 2 at index 0
	- ⏩ `[2, 3, 4, 5, 8]`
---
## ⏱ Time and Space Complexity

| Case    | Time Complexity | Why                                     |
| ------- | --------------- | --------------------------------------- |
| Best    | O(n)            | Already Sorted                          |
| Average | O($n^2$)        | Nested Loop                             |
| Worst   | O($n^2$)        | Reversed Sorted                         |
| Space   | O(1)            | In-place sorting                        |
| Stable  | ✅ Yes           | Does not change order of equal elements |

---
## ✅ When to Use
- Small datasets
- Nearly sorted data(very efficient)
- When stability is important
---
## ⚠️ When Not to Use
- For very large arrays (O($n^2$) performance degrades fast)
---
## 📌 Interview Tip
Insertion Sort is great to understand how in-place sorting works.
It also builds intuition for more complex sorts like Merge Sort or Tim Sort.