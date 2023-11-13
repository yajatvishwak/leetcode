# Problem
https://leetcode.com/problems/two-sum/

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

 

#### Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
Example 2:

Input: nums = [3,2,4], target = 6
Output: [1,2]
Example 3:

Input: nums = [3,3], target = 6
Output: [0,1]
 

### Constraints:

- 2 <= nums.length <= 104
- -109 <= nums[i] <= 109
- -109 <= target <= 109
- Only one valid answer exists.

# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->
- Classic Leetcode question.
- empty dict, to store : value:index
- loop through each num in list, then do target-num
- now the subtraction of this is how much you need to find a solution, check in the dict if this subtraction num exists
- if yes, return current index and the value of that subtraction num as a key
- if no, add this num to the dict -> value:index

# Approach
1. create empty dict to store {value:index}
2. enummerate through every element in the list : index, value
3. subtract target - value = s
4. if s in d, then return [index, d[s]]
5. else add to dict d[s] = index
6. ~~return [] if nothing is found, loop does not complete i.e no pair of numbers found that add up to target~~ the question mentions the 
 
# Complexity
- Time complexity: O(n)
- Space complexity: O(n)

# Code
```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        d = {} # store value:index
        for i,val in enumerate(nums):
            if (target - val) in d:
                return [i , d[(target - val)]]
            else:
                d[val] = i
    return []
```
