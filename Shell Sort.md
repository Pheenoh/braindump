# Shell Sort
#computer-science #algorithm 

Shell sort is an [[algorithm]] that is similar to [[insertion sort]] except it allows for comparisons of elements further in the index to reduce the number of comparisons. This is favorable if elements much later in the array are bigger than the current element.

## Code Example
```python
unsorted_array = [903, 306, 404, 963, 907, 92, 380, 902, 739, 693, 207, 257, 712, 997]

def shell_sort(array, num):
    # Used to track the gap until it is of size 1
    gap = num // 2

    while gap > 0:
        j = gap

        while j < num:
            i = j - gap
            
            while i >= 0:
                if array[i+gap] > array[i]:
                    break
                else:
                    # Swap the elements
                    array[i+gap],array[i] = array[i],array[i+gap]

                i -= gap
            
            j += 1
        gap //= 2

shell_sort(unsorted_array, len(unsorted_array))
print(unsorted_array)
```