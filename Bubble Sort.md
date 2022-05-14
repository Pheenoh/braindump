# Bubble Sort
#computer-science #algorithm 

Sorting [[algorithm]] that works by iterating through an unsorted array and swapping adjacent elements if they are in the wrong order.

## Code Example
```python
unsorted_array = [6,2,19,669,294,210,20]

def bubble_sort(array):
    # Get the length of the array to know where to stop in loops
    n = len(array)

    # Iterate through array
    for i in range(n):
        # Iterate through array from start to last element minus current element
        for j in range(0,(n - 1) - i):
            # If the current array element is greater than the next...
            if array[j] > array[j+1]:
                # Swap them
                tmp = array[j]
                array[j] = array[j+1]
                array[j+1] = tmp

bubble_sort(unsorted_array)

print(unsorted_array)

```