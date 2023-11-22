# Problem

https://leetcode.com/problems/maximum-subarray/description/

Given an integer array nums, find the subarray with the largest sum, and return its sum.


# Intuition
- can be solved with kadanes algorithm
- saw this on neetcode

# Approach
- have 2 variables `currSum` to store the running sum of the numbers
- and `maxSum` to store max, (one of the `currSum` will "qualify" to be `maxSum`)
- loop through each array item
- keep adding each number to `currSum`
- buttttt if the `curSum` is going to be a negative number, reset it to `0`
- update `maxSum` to either be the max of `maxSum` or `currSum`
- return `maxSum`

# Complexity
- Time complexity: O(n)
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: O(n)
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code
```
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        curSum = 0
        maxSum = nums[0]
        for n in nums:
            curSum =  max(curSum, 0) # resets to 0, if curSum goes -ve
            curSum += n
            maxSum= max(curSum, maxSum)
        return maxSum
        
```
