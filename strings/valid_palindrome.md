# Problem
A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.
Given a string s, return true if it is a palindrome, or false otherwise.

# Solution
It's simple.
Use two pointers and check if the selected character is alphanumeric, skip and continue if yes, proceed if no. 
Then, check if the characters at the two pointers are same or not, if no, return false, else, keep checking. return true outside of the while loop.
