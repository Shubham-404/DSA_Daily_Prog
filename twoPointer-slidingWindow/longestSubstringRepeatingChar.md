# Longest Substring Without Repeating Characters

Given a string s, find the length of the longest substring without duplicate characters.

Example 1:

Input: s = "abcabcbb"
Output: 3
Explanation: The answer is "abc", with the length of 3. Note that "bca" and "cab" are also correct answers.


Example 2:

Input: s = "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.


Example 3:

Input: s = "pwwkew"
Output: 3
Explanation: The answer is "wke", with the length of 3.
Notice that the answer must be a substring, "pwke" is a subsequence and not a substring.

# Solution

## Brute force
```cpp
int lengthOfLongestSubstring(string s) {
        int maxLen = 0, n = s.length(), count;
        for (int i = 0; i < n; i++) {
            if (maxLen > n - i + 1)
                return maxLen;
            vector<int> hash(256, 0); // total 256 ascii char possible
            hash[s[i]] = 1;
            count = 1;
            for (int j = i + 1; j < n; j++) {
                if (hash[s[j]] == 1) { // repeating
                    break;
                } else {
                    count++;
                    hash[s[j]] = 1;
                }
            }
            maxLen = max(maxLen, count);
        }
        return maxLen;
    }

```

## Optimal using Two Pointers

```cpp


```