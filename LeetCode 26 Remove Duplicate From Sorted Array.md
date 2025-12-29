# LeetCode 26: Remove Duplicate From Sorted Array

## Given : 
Integer array nums which is sorted in non-decreasing order, 
remove the duplicates in-place such that each unique element appears only once.
The relative order of the elements should be kept the same.

If the unique ele are k then return k, and the order of ele beyond k-1 does'nt matters.

### Intution:

1. using two pointer approach.
2. taking left and right, left will be at first ele and right will be at left + 1.
3. if ele at left is equal to ele at right, then keep moving right pointer forward.
4. if ele at left is not equal to ele at right, then nums[left + 1] = nums[right], and left + 1.
5. at last return k, k = left + 1.

### Algorithm: 
``` java
left = 0, right = 1
loop ( right < nums.length - 1) {
  if(nums[left] != nums[right]){
    nums[left + 1] = nums[right]
    left += 1
  }
  else{
    right++
  }
}

return (left + 1)
```

### Final Code ( Java):
``` java
class Solution {
    public int removeDuplicates(int[] nums) {
        int left = 0, right = 1;
        while(right < nums.length){
            if(nums[left] != nums[right]){
                nums[left + 1] = nums[right];
                left += 1; 
            }
            else{
                right++;
            }
        }
        return (left+1);
    }
}
```








