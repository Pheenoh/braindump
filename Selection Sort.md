# Selection Sort
#computer-science #algorithm 

Selection sort is an [[algorithm]] that works by finding the minimum element of an unsorted array and moving it to the front (assuming ascending sort). This is done by maintaining to sub arrays: a sorted and unsorted array

## Code Example
```python
unsorted_array = [6,2,19,669,294,210,20]

def selection_sort(array):
    n = len(array)

    for i in range(n):
        # Set the current index as the minimum
        min_idx = i

        # Loop through the rest of the array to find if there is a lower minimum
        for j in range(i+1, n):
            # If the current element is smaller than the current know minimum
            # Set that element's index to the new minimum
            if array[min_idx] > array[j]:
                min_idx = j

        # Swap the elements
        array[i], array[min_idx] = array[min_idx], array[i]
        print(array)

selection_sort(unsorted_array)
print(unsorted_array)
```