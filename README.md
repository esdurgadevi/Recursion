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
### Unique Integers - Binary Suffixes
The program must accept an integer N as the input. The program must print the unique integers that are formed by converting the suffixes in the binary representation of N to decimal values. The unique integers must be printed in ascending order.
Boundary Condition(s): 1 <= N <= 10^8

Input Format:
The first line contains N.
Output Format:
The first line contains the unique integers based on the given condition.

Example Input/Output 1:
Input: 12
Output: 0 4 12
Explanation:
Here N = 12.
The binary representation of 12 is 1100.
The suffixes in the binary representation of 12 are 0, 00, 100 and 1100. The unique integers that are formed by converting the above suffixes are 0, 4 and 12. So the integers 0, 4 and 12 are printed in ascending order.

Example Input/Output 2:
Input: 77
Output:1 15 13 77
```java
import java.util.";
public class Hello
{
    public static void main(String[] args)
    {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        ArrayList<Integer> ans = new ArrayList<>();
        while(n>0)
        {
            ans.add(n%2);
            n/=2;
        }
        Collections.reverse(ans);
        ArrayList<Integer> a1 = new ArrayList<>();
        find(a1, ans,0);
        Collections.reverse(a1);
        for(int x:a1) System.out.print(x+" ");
    }
    public static void find(ArrayList<Integer> a1, ArrayList<Integer> ans,int index){
         int sum = 0,g=0;
         if(index>=ans.size()){
             return;
         }
         for(int i=ans.size()-1;i>=index; i--){
              sum=sum+ans.get(i)*(int)Math.pow(2,g++);
          }if(lal.contains(sum)) al.add(sum);
          find(a1, ans, index+1);
   }
}
```
- In this code using recursion we find the each sun sequence number and rint it in ascending order.
### 125. Valid Palindrome
[Leetcode link](https://leetcode.com/problems/valid-palindrome/)
<br>
A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.
Given a string s, return true if it is a palindrome, or false otherwise.

Example 1:
Input: s = "A man, a plan, a canal: Panama"
Output: true
Explanation: "amanaplanacanalpanama" is a palindrome.

Example 2:
Input: s = "race a car"
Output: false
Explanation: "raceacar" is not a palindrome.

Example 3:
Input: s = " "
Output: true
Explanation: s is an empty string "" after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.

Constraints:
1 <= s.length <= 2 * 105
s consists only of printable ASCII characters.

```java
class Solution {
    public boolean isPalindrome(String s) {
        StringBuilder str = new StringBuilder();
        for(int i=0;i<s.length();i++)
        {
            char ch = s.charAt(i);
            if(Character.isDigit(ch) ||  Character.isLetter(ch))
            {
                str.append(Character.toLowerCase(ch));
            }
        }
        boolean ans = find(str.toString(),0);
        return ans;
    }
    public boolean find(String str,int index)
    {
        if(index>=str.length()/2) return true;
        if(str.charAt(index)!=str.charAt(str.length()-index-1))
        {
            return false;
        }
        return find(str,index+1);
    }
}
```
- In this code we find the string is palindrome or not using recursion.
- so first we remove all comma full stop and space from the string and call the recursion function whenever the first and the last character is not equal that time we return the false.
- Otherwise if we croos the half of the string then we return true beacue all that is same.
### Find all factorial numbers less than or equal to n
[Leetcode link](https://www.geeksforgeeks.org/problems/find-all-factorial-numbers-less-than-or-equal-to-n3548/0?problemType=functional&difficulty%255B%255D=-1&page=1&query=problemTypefunctionaldifficulty%255B%255D-1page1)
<br>
A number n is called a factorial number if it is the factorial of a positive integer. For example, the first few factorial numbers are 1, 2, 6, 24, 120,
Given a number n, the task is to return the list/vector of the factorial numbers smaller than or equal to n.

Examples:
Input: n = 3
Output: 1 2
Explanation: The first factorial number is 1 which is less than equal to n. The second number is 2 which is less than equal to n,but the third factorial number is 6 which is greater than n. So we print only 1 and 2.
Input: n = 6
Output: 1 2 6
Explanation: The first three factorial numbers are less than equal to n but the fourth factorial number 24 is greater than n. So we print only first three factorial numbers.
Expected Time Complexity: O(k), Where k is the number of factorial numbers.
Expected Auxiliary Space: O(1)

Constraints:
1<=n<=1018
```java
class Solution {
    static ArrayList<Long> factorialNumbers(long n) {
        ArrayList<Long> ans  = new ArrayList<>();
        find(n,ans,1);
        return ans;
    }
    static void find(long n,ArrayList<Long> ans,int index)
    {
        long p =1;
        for(int i=1;i<=index;i++)
        {
            p=p*i;
        }
        if(p>n) return;
        ans.add(p);
        find(n,ans,index+1);
    }
}
```
