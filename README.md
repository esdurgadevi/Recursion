# Recursion
### 342. Power of Four
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
### 231. Power of Two
[LeetCode Link](https://leetcode.com/problems/power-of-two/description/)
```Java
class Solution {
    public boolean isPowerOfTwo(int n) {
        if(n==1) return true;
        if(n<=0) return false;
        return n%2==0 && isPowerOfTwo(n/2);
        
    }
}
```
- Same as the previous problem.
### 509. Fibonacci Number
[LeetCode Link](https://leetcode.com/problems/fibonacci-number/submissions/1322730269)
```Java
class Solution {
    public int fib(int n) {
        if(n<=1) return n;
        return fib(n-1)+fib(n-2);
    }
}
```
- This function will return the fibonacci sum of the numbers 'n'
- Example if n=3 then 0+1+1=2 this function return 2
- Always first and second number in fibonacci series is 0 and 1 so i will return n whenever n is less then or equal to 1 **n<=1**
- other wise i return fib(n-1)+fib(n-2) that is i add the n-1 and n-2 number.
  <hr />
  <img width="762" alt="image" src="https://github.com/user-attachments/assets/1f9ba0ad-d528-4f47-813d-408e686a2aa6">


