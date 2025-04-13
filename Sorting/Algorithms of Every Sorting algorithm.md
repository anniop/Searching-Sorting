## 🔁 1. Bubble Sort (Ascending Order)
**Idea**: Keep swapping adjacent elements if they are in the wrong order.
#### Steps:
1. Loop from `i = 0` to `n -1`
2. For each pass, loop `j` from `0` to `n - i - 2`
	1. if `arr[j] > arr[j + 1]`, swap them
3. Repeat until no swaps are needed
---
## 🔽 2. Bubble Sort (Descending Order)
**Idea**: Keep swapping if the left element is smaller than the right one.
#### Steps:
1. Loop from `i = 0` to `n-1`
2. For each pass, loop `j` from `0` to `n - i -2`:
	1. If `arr[j] < arr[j + 1]`, swap them.
---
## 🔍 3. Selection Sort (Ascending)
**Idea**: Find the smallest element from the unsorted part and put it at the front.

#### Steps:
1. Loop from `i = 0` to `n - 2`
2. Assume the smallest is at `minIndex = i`
3. Loop from `j = i + 1` to `n - 1`:
	1. If`arr[j] < arr[minIndex]`, update `minIndex`
4. After the loop, swap `arr[i]` and `arr[minIndex]`
---
## 🔼 4. Selection Sort (Descending)

**Idea:** Find the largest and place it at the front of the unsorted part.

### Steps:
1. Loop from `i = 0` to `n-2`
2. Assume the largest is at `maxIndex = i`
3. Loop `j = i+1` to `n-1`:
    - If `arr[j] > arr[maxIndex]`, update `maxIndex`
4. Swap `arr[i]` and `arr[maxIndex]`
----
## 🧠 5. Insertion Sort (Ascending)
**Idea**: Take one element and insert it into its correct position in the sorted part of the array.

#### Steps:
1. Loop from `i = 1` to `n - 1`
2. Set `key = arr[i]`, and `j = i - 1`
3. While `j >= 0` and `arr[j] > key`:
	1. Shift `arr[j]` right
	2. Decrease `j`
4. Place `key` at `arr[j + 1]`
---
## ⬇️ 6. Insertion Sort (Descending)
Same logic, but reverse the comparison
#### Steps:
1. Loop `i = 1`to `n - 1`
2. Set `key = arr[i]`, `j = i - 1`
3. While `j >= 0 && arr[j] < key`:
	1. Shift `arr[j]` right
	2. Decrease `j`
4. Place `key` at `arr[j + 1]`
---
## ⚡ 7. Quick Sort (Ascending Order)
**Idea**:Choose a pivot, place it in its correct position, and recursively sort the left and right parts.

---
### 🔁 Algorithm (Lomuto Partition Scheme – Pivot is Last Element):
1. If start < end:
     - Choose pivot = arr[end]
     - Partition the array into two parts:
         → Left: elements <= pivot
         → Right: elements > pivot
2. After partition, pivot is at correct position:
     - Recursively apply quick sort to left part: start to pivotIndex - 1
     - Recursively apply quick sort to right part: pivotIndex + 1 to end
### 🧠 Partitioning:
1. Set index = start - 1
2. Loop j from start to end - 1:
     - If arr[j] <= pivot:
         - index++
         - swap arr[index] and arr[j]
3. Finally, swap arr[index + 1] and arr[end] (pivot)
4. Return index + 1 (new position of pivot).
---
## 🧩 8. Merge Sort (Ascending Order)
**Idea**: Divide the array into halves, sort each half, and merge them back in sorted order.

---
### 🔁 Algorithm:
1. If start < end:
     - Find mid = (start + end) / 2
2. Recursively call:
     - mergeSort(arr, start, mid)
     - mergeSort(arr, mid + 1, end)
3. Merge the two sorted halves:
     - Create temporary arrays
     - Compare and merge elements from left and right into a sorted array
     - Copy merged array back to original
---
### 🧠 Merge Step:
1. Create two temporary arrays:
     - left = arr[start...mid]
     - right = arr[mid+1...end]
2. Use three pointers:
     - i for left, j for right, k for original array
3. Compare left[i] and right[j]:
     - Place smaller into arr[k], then increment pointers
4. After one is exhausted, copy the remaining elements
---
