# Intuition
We'll create two integer hash arrays for both the strings and then we'll check if the hash of both the arrays are same then the strings are anagram otherwise no.

# Approach
Edge case: if the length of the strings are not same then straigh away return false.

Create two integer hash array of length 26(representing the 26 alphabets) for both strings.

Start a loop from zero to the end of string and increase the value of alphabet in the integer hash array using logic -> hasharr[s.charAt(i) - 'a']++

At last check if the both the arrays are same or not using Java built-in method Arrays.equals(arr1,arr2)

If arrays are same return true or else return false
# Complexity
- Time complexity: O(n)
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: O(1)
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code
```java []
class Solution {
    public boolean isAnagram(String s, String t) {
        
        if(s.length() != t.length())
            return false;
        
        int sArr[] = new int[26];
        int tArr[] = new int[26];

        for(int i = 0; i < s.length(); i++){
            sArr[s.charAt(i) - 'a']++;
            tArr[t.charAt(i) - 'a']++;
        }

        if(Arrays.equals(sArr,tArr))
            return true;
        
        return false;
    }
}
```
