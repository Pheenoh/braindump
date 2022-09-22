# Binary Search
#computer-science #algorithm 

Binary search is a search [[algorithm]] that is used with sorted arrays. Since the array is sorted, we can continually split the array in half and check to see which half the value is in until we find it.

## Code Example
```python
sorted_array = [6,7,10,12,15,19,23,26,29,40,50,69.78,89]

def binary_search(array: list, start: int, stop: int, value: int) -> int:
    if stop >= start:
        mid = start + (stop - start) // 2
        if array[mid] == value:
            return mid
        
        elif array[mid] > value:
            return binary_search(array, start, mid-1, value)
        
        else:
            return binary_search(array, mid+1, stop, value)
    else:
        return -1

print("Value 15 is in the array at index:", binary_search(sorted_array,0,len(sorted_array)-1,15))

```