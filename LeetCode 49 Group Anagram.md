# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->
We'll be using a HashMap for storing the values and the anagram.
# Approach
<!-- Describe your approach to solving the problem. -->
1. Declare a HashMap<String,List<String>>
2. Iterate over the first ele of the given array
3. store the first ele into a char Array and sort the array
4. store the sorted array inside a string variable 
5. check if the string variable is present already inside the map, if not then add the string variable with a empty list
6. after that add the ele into the arraylist
7. if it does exist before then also do the step 6
8. at last return a new arraylist with the values of hashmap

# Complexity
- Time complexity:O(n.klogk)
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity:O(n.k)
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code
```java []
class Solution {
    public List<List<String>> groupAnagrams(String[] strs) {
        HashMap<String,List<String>> map = new HashMap<>();
        
        for(String word : strs){
            char[] arr = word.toCharArray();
            Arrays.sort(arr);
            String str = new String(arr);

            if(!map.containsKey(str))
                map.put(str,new ArrayList<>());

            map.get(str).add(word);
        }
        return new ArrayList<>(map.values());
    }
}
```
