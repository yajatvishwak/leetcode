# Problem
https://leetcode.com/problems/valid-anagram/
Given two strings s and t, return true if t is an anagram of s, and false otherwise.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.



# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->
- saw this on neetcode
- this is smarterrrr
# Approach
<!-- Describe your approach to solving the problem. -->
- just sort the string
- and then compare if they are equal
- if they are anagrams, they'll arrange themselves in the same order
# Complexity
- Time complexity: O(nlogn)

- Space complexity: O(n)
# Code
```
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        return sorted(s) == sorted(t)
```
