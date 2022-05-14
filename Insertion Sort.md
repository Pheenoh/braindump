# Insertion Sort
#computer-science #algorithm 

Insertion sort is an [[algorithm]] that works by comparing two adjacent numbers in an array and moving the greater of the two numbers further into the array (similat to sorting cards in your hand).

## Code Example
```python
unsorted_array = [12,11,13,5,6]

def insertion_sort(array):
    # Get the length of the array to know where to stop in loops
    n = len(array)

    # Iterate through array
    for i in range(n):

        # Store the current element idx as the key
        key = array[i]

        # Store previous element idx
        j = i - 1

        # Continue decreasing j (checking previous element) While the previous element idx 
        # is gt or equal to 0 and the previous element is greater than the current
        while j >= 0 and key < array[j]:
            array[j+1] = array[j]
            j -= 1
        array[j+1] = key
        print(array,", index: ",i)


insertion_sort(unsorted_array)
print(unsorted_array)

```