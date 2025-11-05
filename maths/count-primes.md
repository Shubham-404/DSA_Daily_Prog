# Problem

## Given an integer n, return the number of prime numbers that are strictly less than n.

# Solution

## using for loops is possible but take eternity to solve it.
## so we will use something famously termed as : `Sieve of Erathosthenes`

we initially assume all the numbers are prime then start from beginning. 
as counting starts with 2 which is prime, we keep eliminating all the multiples of 2 from 2*2 to n.

Similarly move forward for other numbers as well, and at the end only prime numbers will remain as true. 

count the prime numbers and return ans.

```cpp
class Solution {
public:
    int countPrimes(int n) {
        if(n<2) return 0;
        vector<int> isPrime(n, true);
        isPrime[0] = isPrime[1] = false;
        // int count = 0;
        for(int i = 2; i*i<n; i++){
            if(isPrime[i]){
                // count ++;
                for(int j=i*i; j<n; j+=i){
                    isPrime[j] = false;
                }
            }
        }
        return count(isPrime.begin(), isPrime.end(), true);
    }
};
```