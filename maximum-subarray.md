# Problem
[https://leetcode.com/problems/valid-anagram/](https://leetcode.com/problems/maximum-subarray/)

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
- Create 2 dicts with {char:count} for both the inputstrings
- Loop and check if both dict have same count value for each char
- Return false if not both the strings do not have the same length, because then 100000000% they are not anagrams

# Approach
<!-- Describe your approach to solving the problem. -->
1. declare 2 dicts
2. check length of the two strings, chuck false if they are not same
3. ~~loop through each string and construct the dicts~~ you have already validated that the strings are going to be of the same length, so just loop through one string, and add each char to the dict based on index as the key and the value will be one increment of it's previous value, so `dict[s[i]] = dict.get(s, 0) + 1` 
4. loop through one of the constructed dict and ~~check if each key exists in both the dicts~~ check if key present in the other dict and also that the value of the key in both the dicts are equal (checking if the count for the char is same)
5. if above conditions fail even for one iteration, return false
6. if above conditions pass will not even one fail, return true

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
