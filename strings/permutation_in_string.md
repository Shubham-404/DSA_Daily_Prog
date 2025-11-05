# Problem
Given two strings s1 and s2, return true if s2 contains a permutation of s1, or false otherwise.

In other words, return true if one of s1's permutations is the substring of s2.

# Solution
## Sliding Window (not recursion here)

- Use a hashmap or for limited characters (a-z in this case) you can also use arr[26], to store frequency of the characters of the string.
- for a string to be a permutation of the other, the size and frequency of the string must same as of the selected window of the other string.
- so, for each window of second string (window size = size of first string), check frequency of each character and match it with the freqency array/hashmap of string2.

```cpp
class Solution {
public:
    bool isFreqSame(int freq1[], int freq2[]) {
        for (int i = 0; i < 26; i++) {
            if (freq1[i] != freq2[i])
                return false;
        }
        return true;
    }

    bool checkInclusion(string s1, string s2) {
        int freq1[26] = {0}; // since elements are limited we're using array
        for (char ch : s1) {
            freq1[ch - 'a']++;
        }
        int n1 = s1.length();
        int n2 = s2.length();

        for (int i = 0; i <= n2 - n1; i++) {
            int windFreq[26] = {0}; // window frequncy array
            for (int j = i; j < i + n1; j++) {
                windFreq[s2[j] - 'a']++;
            }
            if (isFreqSame(freq1, windFreq))
                return true;
            
        }
        return false;
    }
};
```