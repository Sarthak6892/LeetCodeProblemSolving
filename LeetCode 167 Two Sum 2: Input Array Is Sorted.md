# Leetcode 167 Two Sum 2: Input Array Is Sorted

## What Question Says: 
You are given a sorted array of integer , numbers[] = {2, 7, 9, 11, 15}, target = 9.
Return the indices where the sum of ele at indices is equal to target.

Op -> [1,2] , explain -> nums[1] + nums[2] = 2+7 = 9.

### Intution:
1. Using Two Pointer Approach.

### Algorithm:

``` java
left = 0, right = numbers.length -1
loop ( left < right) {
  sum = numbers[left] + numbers[right]
  if( sum == target)
    return ( left + 1) and ( right + 1 )  -> +1 because of zero based indexing.
  else if( sum > target)
    right--;
  else
     left++;
}

return empty array

```

### Final Code (java) :
```java

class Solution {
    public int[] twoSum(int[] numbers, int target) {
        int left = 0, right = numbers.length - 1;
        while(left < right){
            int sum = numbers[left] + numbers[right];
            if(sum == target)
                return new int[] {left+1,right+1};
            else if(sum > target)
                right--;
            else
                left++;
        }
        return new int[] {};
    }
}

```
