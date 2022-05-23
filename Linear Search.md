# Linear Search
#computer-science #algorithm 

Linear search is a search [[algorithm]] that searches for a value in an array but iterating through each element of the array and checking each value until finding the one that is being searched for.

## Code Example
```python
unsorted_array = [12,11,13,5,6]

def linear_search(array: list, flag: int) -> int:
    n = len(array)
    for i in range(n):
        if array[i] == flag:
            return i
    
    return -1

print("Flag 12 is at index:", linear_search(unsorted_array,11))
```