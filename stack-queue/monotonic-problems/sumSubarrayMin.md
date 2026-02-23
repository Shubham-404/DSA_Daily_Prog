# Sum of Subarray Minimums

Given an array of integers arr, find the sum of min(b), where b ranges over every (contiguous) subarray of arr. Since the answer may be large, return the answer modulo 109 + 7.

 

Example 1:

Input: arr = [3,1,2,4]
Output: 17
Explanation: 
Subarrays are [3], [1], [2], [4], [3,1], [1,2], [2,4], [3,1,2], [1,2,4], [3,1,2,4]. 
Minimums are 3, 1, 2, 4, 1, 1, 2, 1, 1, 1.
Sum is 17.

Example 2:

Input: arr = [11,81,94,43,3]
Output: 444


# Solution
Brute force in O(N2).
```cpp
int sumSubarrayMins(vector<int>& arr) {
    int ans = 0, mod = (int)(1e9 + 7), n = arr.size();
    for (int i = 0; i < n; i++) {
        int minm = arr[i];
        for (int j = i; j < n; j++) {
            minm = min(minm, arr[j]);
            ans = (ans + minm) % mod;
        }
    }
    return ans;
}
```
*Gives TLE*


Optimal using

```cpp


```
