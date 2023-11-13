# Problem
https://leetcode.com/problems/valid-anagram/

Given two strings s and t, return true if t is an anagram of s, and false otherwise.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.
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
- Time complexity: O(n)

- Space complexity: O(n)

# Code
```
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        s_count = {}
        t_count = {}
        
        if len(s) != len(t):
            return False

        for index in range(len(s)):
            s_count[s[index]] = s_count.get(s[index], 0) + 1
            t_count[t[index]] = t_count.get(t[index], 0) + 1
        
        for key in s_count:
            if key in t_count and key in s_count and s_count[key] == t_count[key]:
                pass
            else:
                return False
        return True
            

        
```
