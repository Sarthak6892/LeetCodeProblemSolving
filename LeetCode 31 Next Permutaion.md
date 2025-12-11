# LeetCode 31 Next Permutation

What Question Says: given a array of integer nums[].
nums[] = [1 2 3] 
return the next permutaion of this give array in lexicographical order.

## Intution: 
1) find the longest prefic match ( finding the breaking point )
*starting from the second last ele of the array and checking if the ele next to it is greater than or not.
*if the ele next to it is greater than means that's the breaking point.

2) if no breaking_index is found then that means the arrays given is the last permutation according to the lexicographical order so in that case return the reverse of array. 

3) start from last of the array and find the ele just greater than the ele at the breaking_index.

4) swap the first ele that is greater than the ele at breaking_index.

5)reverse the array beyond the breaking_index.

## Algorithm: 
```java
int breaking_index = -1
loop( i = nums.length - 2 to 0){
  if( nums[i] < nums[i+1] ){
      breaking_index = i
      break the loop
  }
}

if(breaking_index == -1){
  reverse the array
  return ;
}

loop( i = nums.length - 1 to breaking_index){
  if(nums[i] > nums[beraking_index] ){
      swap ( nums[i] , nums[breaking_index]);
      break the loop
  }
}

left = breaking_index + 1 , right = nums.length - 1
loop( left < right ){
swap( nums[left], nums[right])
}
```

## Final Code (Java)
```java
class Solution {
    public void nextPermutation(int[] nums) {
        int breakingIndex = -1;

        int i = nums.length - 2;
        // this loop finds the breaking index.
        while( i >= 0){
            if(nums[i] < nums[i+1]){
                breakingIndex = i;
                break;
            }
            i--;
        }

        // this condition cover the edge case, that if the array do not have any next permutation then it will reverse the array. 
        if(breakingIndex == -1){
            reverseArray(nums, 0, nums.length - 1);
            return;
        }

        // loop to swap the ele at the breaking index and placing the ele which is just greater than it not the greatest, just greater.
        int j = nums.length - 1;
        while(j > breakingIndex){
            if(nums[j] > nums[breakingIndex]){
                swap(nums,j ,breakingIndex);
                break;
            }
            j--;
        }

        // this function reverse the rest of the array
        reverseArray(nums, breakingIndex + 1, nums.length - 1);
    }

    void reverseArray(int[] nums, int left, int right){
        while(left < right){
            swap(nums,left,right);
            left++; right--;
        }
    }

    void swap(int[] nums , int left, int right){
            int temp = nums[left];
            nums[left] = nums[right];
            nums[right] = temp;
    }
}
