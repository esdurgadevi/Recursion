# Recursion
## 342. Power of Four
[LeetCode Link](https://leetcode.com/problems/power-of-four/submissions/1322706922)
```Java
class Solution {
    public boolean isPowerOfFour(int n) {
        if(n==1) return true;
        if(n<=0) return false;
        return n%4==0 && isPowerOfFour(n/4);
    }
}
```
- I will return whenever the n is one because after divide the number by 4 finally it will give 1 sometimes n=1 that time 4 power 0 will give one so
all the possible ways are if n==1 then it is true whenever n<=0 it will false (negative numbers)
- Here one notepoint that is 5/4 also give one that is 5/4==1.25 but the function will take only integer so it will take one and then check if n==1
then return true but 5 is not a power of 4 in this reason we check n%4==0 and then call the function.
