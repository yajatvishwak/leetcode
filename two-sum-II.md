# Problem
https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/description/

## Two Sum II - Input Array Is Sorted
Given a 1-indexed array of integers numbers that is already sorted in non-decreasing order, find two numbers such that they add up to a specific target number. Let these two numbers be numbers[index1] and numbers[index2] where 1 <= index1 < index2 < numbers.length.

Return the indices of the two numbers, index1 and index2, added by one as an integer array [index1, index2] of length 2.

The tests are generated such that there is exactly one solution. You may not use the same element twice.

Your solution must use only constant extra space.

# Intuition
- saw this on neetcode
- solve using 2 pointer since array is sorted
# Approach
<!-- Describe your approach to solving the problem. -->
- Start off with 2 pointer l and r pointing to the start and the end of the list
- `curSum`, another variable will store sum of two variables
- loop till `l` and `r` pointers cross each other `l < r`
- add `l` and `r` values to `curSum`
- if `curSum < target`, move i pointer to the next element, because we know that the sum is small and we need a bigger number to reach target. also we know that the next number will be a `bigger number` since the array is sorted.
- similarly if `curSum > target`, move `j` pointer to previous element because now the curSum is bigger than `target` and we need a `smaller number` to sum. and we know that previous element is the smaller number because list is sorted
# Complexity
- Time complexity:O(n)
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: O(n)
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code
```
class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        l,r = 0, len(numbers) -1
        curSum = 0
        while(l<r):
            curSum = numbers[l]+numbers[r]
            if curSum < target:
                l+=1
            elif curSum > target:
                r-=1
            else:
                return [l+1,r+1]
```
