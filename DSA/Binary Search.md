### Binary Search Applications

#### Introduction
**Binary search** is originally taught as an efficient searching algorithm having a **time complexity of O(log n).** This is only one of the applications of binary search. To fully understand this technique, it is best to conceptualize binary search differently.

If we think of binary search as an array of consecutive **boolean** values, then we can extend what the algorithm is capable of. There are many ways to modify binary search to adjust to the specific problem at hand.

For example, the basic example of binary search looks like the following:
```python
class Solution: 
	def search(self, nums: List[int], target: int) -> int: 
		left = 0
		right = len(nums) - 1
		while left <= right:
			mid = left + (right - left) // 2
			
			if nums[mid] == target: 
				return mid
			
			if nums[mid] < target:
				left = mid + 1
			else:
				right = mid - 1
				
		return -1
```

There are many different ways that we can modify the code above. We can do the following:
- Change `right = len(nums)` instead of `right = len(nums) - 1`
    - This variation allows the algorithm to go outside the length of the array. This is helpful for questions like “where should I add a value **after**”. It would indicate to add it at the end of the array.
- Change `left = -1` instead of `left = 0`
    - This variation allows the algorithm to go outside the length of the array. This is helpful for questions like “where should I add a value **before**”. It would indicate to add it at the start of the array.
- Change `while left < right` instead of `while left ≤ right`
    - This variation allows the algorithm to be less strict. This also means that you would not check for equivalence inside the while loop.
- Change `mid = left + (right - left + 1) // 2` instead of `mid = left + (right - left) // 2`
    - This variation allows the algorithm to round up instead of rounding down. This is helpful when you want to make sure that you do not get an out of bounds error when changing the left and right bounds to `-1` and `len(nums)`, respectively.
    - If you want to have `left = -1` and `right = len(nums) - 1`. You want to do `mid = left + (right - left + 1) // 2` so that you would never encounter the program doing `nums[-1]`.
    - If you want to have `left = 0` and `right = len(nums)`. You want to do `mid = left + (right - left) // 2` so that you would never encounter the program doing `nums[len(nums)]`.

### Examples

> [!example] Example 1
> Find the first True
> - Example:
> 	- [False, False, False, **True**, True, True, True] 
> 		- returns 3
> 	- [**True**, True, True, True, True, True, True] 
> 		- returns 0
> 	- [**False**, False, False, **True**, True, True, True] 
> 		- returns 7

```python
class Solution: 
	def search(self, nums: List[int], target: int) -> int: 
		left = 0 
		right = len(nums) 
		
		while left < right: 
			mid = left + (right - left) // 2 
			
			if nums[mid]: 
				right = mid 
			else: 
				left = mid + 1 
	
		return left
```

> [!example] Example 2
> Find the first False
> - Example:
> 	- [True, True, True, True, **False**, False, False] 
> 		- returns 4
> 	- [True, True, True, True, True, True, True] 
> 		- returns 7
> 	- [**False**, False, False, False, False, False, False] 
> 		- returns 0

```python
class Solution: 
	def search(self, nums: List[int], target: int) -> int:
		left = 0 
		right = len(nums) 
		
		while left < right: 
			mid = left + (right - left) // 2 
			
			if nums[mid]: 
				left = mid + 1 
			else: 
				right = mid 
				
		return left
```

> [!example] Example 3
> Find the last True
> - Example:
> 	- [True, True, True, True, False, False, False]
> 		- returns 3
> 	- [True, True, True, True, True, True, True] 
> 		- returns 6
> 	- [False, False, False, False, False, False, False] 
> 		- returns -1

```python
class Solution: 
	def search(self, nums: List[int], target: int) -> int: 
		left = -1
		right = len(nums) - 1
		
		while left < right: 
			mid = left + (right - left + 1) // 2 
			
			if nums[mid]: 
				left = mid
			else: 
				right = mid - 1
				
		return left
```

> [!example] Example 4
> Find the last False
> - Example:
> 	- [False, False, False, **False**, True, True, True] 
> 		- returns 3
> 	- [True, True, True, True, True, True, True] 
> 		- returns -1
> 	- [False, False, False, False, False, False, **False**]
> 		- returns 6

```python
class Solution: 
	def search(self, nums: List[int], target: int) -> int: 
		left = -1 
		right = len(nums) - 1 
		
		while left < right: 
			mid = left + (right - left + 1) // 2 
			
			if nums[mid]: 
				right = mid - 1 
			else: 
				left = mid 
		
		return left
```