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
### 273. Integer to English Words
[Leetcode link](https://leetcode.com/problems/integer-to-english-words/description/?envType=daily-question&envId=2024-08-07)
<br>
Convert a non-negative integer num to its English words representation.

Example 1:
Input: num = 123
Output: "One Hundred Twenty Three"

Example 2:
Input: num = 12345
Output: "Twelve Thousand Three Hundred Forty Five"

Example 3:
Input: num = 1234567
Output: "One Million Two Hundred Thirty Four Thousand Five Hundred Sixty Seven"

Constraints:
0 <= num <= 231 - 1

```java
class Solution {
    String[] s1 = {"","One","Two","Three","Four","Five","Six","Seven",
    "Eight","Nine","Ten","Eleven","Twelve","Thirteen","Fourteen"
    ,"Fifteen","Sixteen","Seventeen","Eighteen","Nineteen"};
    String[] s2 = {"","","Twenty","Thirty","Forty","Fifty","Sixty","Seventy",
    "Eighty","Ninety"};
    public String numberToWords(int num) {
        if(num==0) return "Zero";
        String[] o ={"","Thousand","Million","Billion"};
        int i=0;
        String words ="";
        while(num>0)
        {
            if(num%1000 != 0) words = get(num%1000)+o[i]+" "+words;
            num/=1000;
            i++;
        }
        return words.trim();
    }
    public String get(int n)
    {
        if(n==0) return "";
        else if(n<20) return s1[n]+" ";
        else if(n<100) return s2[n/10]+" "+get(n%10);
        else return s1[n/100]+" Hundred "+get(n%100);
    }
}
```
- In this code first we initialize one string array by one to nineteen number.
- Then we initaialize by twenty thirty numbers upto ninety.
- then initialize the thousand million and billion.
- run a while loop by num>0
- We see the pattern is we pair up every three numbers from the last the second pair always be like one hundred twenty three thousand.
- Next one hundred twenty three million
- then one hundred twenty three billion
- This will continue.
- so call the function get of by every three digit.
- in the get of function first n is >100 so we get the value in s1 by n/100 and repeatly call the function get(n%100) that is last two digit.
- Now n become two digit so it will go to the <100 condition so we call the s2 function then only we get twenty thirty according to the number and repeatly call get(n%10) that is one digit number.
- So now we call s1[n] then we return.
- the returned word will add to the words.
- we remove the extra space by trim() function.
> [Refernce](https://www.youtube.com/watch?v=SCtIlKd3mDM)

