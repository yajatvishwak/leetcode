# Problem
https://leetcode.com/problems/maximum-subarray/description/


Given an integer array nums, find the subarray with the largest sum, and return its sum.

Example 1:

Input: nums = [-2,1,-3,4,-1,2,1,-5,4]

Output: 6

Explanation: The subarray [4,-1,2,1] has the largest sum 6.

Example 2:

Input: nums = [1]

Output: 1

Explanation: The subarray [1] has the largest sum 1.

Example 3:

Input: nums = [5,4,-1,7,8]

Output: 23

Explanation: The subarray [5,4,-1,7,8] has the largest sum 23.


# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->
- find out each possible combination
- sum its values and keep a record of max sum

# Approach
<!-- Describe your approach to solving the problem. -->
1. set max to inf
2. loop through each element - `i` to `n`
3. inner loop through each element starting from `i` to `n`
4. update m to be the max of itself or sum(from i to j+1)
5. return m

# Complexity
- Time complexity: O(n2) vvvvvvv bad

- Space complexity: O(n)

# Code
```
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        if not nums:
            return 0
        m = float('-inf')
        for i in range(len(nums)):
            for j in range(i,len(nums)):
                m = max(m ,sum(nums[i:j+1]) )
        return m
          
```
