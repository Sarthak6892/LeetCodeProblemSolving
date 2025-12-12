# LeetCode 412 FizzBuzz

## What Question Says: 
1. Given a integer n.
2. Return a string array, if n is divisible by 3 and 5 then arr[i] = "FizzBuzz"
3. if n is divisible by 3 only then arr[i] = "Fizz"
4. if n is divisible by 5 only then arr[i] = "Buzz"
5. if n neither divisible 3 nor 5 then arr[i] = "i"

To easy question no need for intution and algo.

### Final Code (java)
```java
class Solution {
    public List<String> fizzBuzz(int n) {
        List<String> ans = new ArrayList<>();
        for(int i = 1; i <= n ; i++){
            if( i % 3 == 0 && i % 5 == 0)
                ans.add("FizzBuzz");
            else if( i % 3 == 0)
                ans.add("Fizz");
            else if( i % 5 == 0)
                ans.add("Buzz");
            else
                ans.add(i+"");
        }
        return ans;
    }
}
```
