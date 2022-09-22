# Merge Sort
#computer-science #algorithm 

The merge sort [[algorithm]] works by splitting the unsorted array into seperate subarrays continuously, doing individual comparisons between all subarrays and merging them back together.

![[Pasted image 20220514160034.png]]

## Code Example
```python
unsorted_array = [903, 306, 404, 963, 907, 92, 380, 902, 739, 693, 207, 257, 712, 997]

def merge_sort(array):
    # Get the length of the array to know where to stop in loops
    n = len(array)

    # Since this is recursive, only run this check when the array is still bigger than one
    if n > 1:
        
        arr_midpoint = n // 2

        # split the array into two
        left_arr = array[:arr_midpoint]
        right_arr = array[arr_midpoint:]

        # Recursive calls to merge sort the arrays. By design, this will sort the entire first half first, then the second half
        merge_sort(left_arr)
        merge_sort(right_arr)

        i = j = k = 0

        # While i and j are not bigger than their respective array lengths, continue increasing the index we've gone through them all
        while i < len(left_arr) and j < len(right_arr):
            # Check if the current index in the left array is bigger than the current index in the right array
            if left_arr[i] < right_arr[j]:
                # If it is, set that element in the current array and iterate
                array[k] = left_arr[i]
                i += 1
            else:
                # Else, do the opposite in the right array
                array[k] = right_arr[j]
                j += 1

            k += 1
        

        while i < len(left_arr):
            array[k] = left_arr[i]
            i += 1
            k += 1

        while j < len(right_arr):
            array[k] = right_arr[j]
            j += 1
            k += 1

merge_sort(unsorted_array)

print(unsorted_array)

```