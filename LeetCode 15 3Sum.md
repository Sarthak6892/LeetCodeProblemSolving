# LeetCode 15 3Sum
## What Question Says: 
1) Given an integer array,
nums = [-1 0 1 2 -1 -4].
2) Return triplet (nums[i] , nums[j], nums[k] )
where i != j , j != k , k != i
3) nums[i] + nums[j] + nums[k] = 0

### Intution:
1) Using HashSet because it does not store the duplicate values and storing List of type Integer.
2) Using two pointer approach.
3) Use of nested loops.
4) Covering the edge case ( if nums == null or nums length is less than 3)

### Algorithm:

``` java
if(nums is null or nums length is less than 3){
  then return empty ArrayList
}

create new HashSet<List<Integer>> 

outerloop( i = 0 to nums.length -2){
  left = i+1, right = nums.length -1
  innerloop(left < right){
      sum = nums[i] + nums[left] + nums[right]
      if ( sum == 0){
          add in hashset(nums[i], nums[j], nums[k])
          left++ , right--
      }
      else if (sum < 0){
          left++
      }
      else right--  
  }
  i++
}
```

### Final Code (java)
``` java
class Solution {
    public List<List<Integer>> threeSum(int[] nums) {
// covering edge case where either the nums is null or it's length is less than 3.
        if(nums == null || nums.length < 3)
            return new ArrayList<>();
        
        // creating HashSet of List of type Integer, using hashset because it only keeps the uniqe values.
        HashSet<List<Integer>> set = new HashSet<>();

        Arrays.sort(nums);

        // fixing iterator and using two pointer approach
        int i = 0;
        while( i < nums.length - 2){
            int left = i +1; int right = nums.length - 1;
            while(left < right){
                int sum = nums[i] + nums[left] + nums[right];
                if(sum == 0){
                    set.add(Arrays.asList(nums[i], nums[left], nums[right]));
                    left++; right--;
                }
                else if(sum < 0)
                    left++;
                else
                    right--;
            }
            i++;
        }
        return new ArrayList<>(set);
    }
}
```








