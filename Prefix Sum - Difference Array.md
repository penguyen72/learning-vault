One application of the prefix sum is to create a difference array. The purpose of the difference array is to allow us to perform an update on a range of elements in a list in $O(1)$ time instead of iterating through the elements one by one, assuming that the update is a constant value

The brute force approach to apply $Q$ range updates to $N$ elements in an array would be to iterate through range and update the corresponding elements. This would result in a $O(NQ)$ run time complexity

Instead, it is possible to update the values in $O(1)$ time and then construct the array using the difference array in $O(N)$ time
### Example
$queries = [[0,1,3], [2,4,5]]$
$$
diff = [0,0,0,0,0,0,0]
$$$$
diff = [3,0,2,0,0,-5,0]
$$$$
nums = [3,3,5,5,5,0,0]
$$
