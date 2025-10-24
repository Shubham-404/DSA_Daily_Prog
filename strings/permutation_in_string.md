# Problem
Given two strings s1 and s2, return true if s2 contains a permutation of s1, or false otherwise.

In other words, return true if one of s1's permutations is the substring of s2.

# Solution
## Sliding Window (not recursion here)

- Use a hashmap or for limited characters (a-z in this case) you can also use arr[26], to store frequency of the characters of the string.
- for a string to be a permutation of the other, the size and frequency of the string must same as of the selected window of the other string.
- so, for each window of second string (window size = size of first string), check frequency of each character and match it with the freqency array/hashmap of string2.
