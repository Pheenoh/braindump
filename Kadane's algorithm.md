# Kadane's Algorithm
#computer-science #algorithm 

Kadane's [[algorithm]] finds the largest sum of elements in a fixed width subarray.

## Code Example
```python
random_array = [-24,-5,3,95,8,10,39]

import sys
def max_sum_subarray(array: list, size: int):
    max_so_far = sys.maxsize - 1
    final_max = 0
    for i in range(0, size):
        final_max += array[i]
        if max_so_far < final_max:
            max_so_far = final_max
        
        if final_max < 0:
            final_max = 0
    
    return final_max

print("Maximum contiguos sum is",max_sum_subarray(random_array,len(random_array)))
```