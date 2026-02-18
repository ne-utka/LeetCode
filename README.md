# LeetCode
Java repos for resolving problemset/algorithms

1. Two Sum

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.
You can return the answer in any order.

            class Solution {
              int first_number, second_number = 0;
              public int[] twoSum(int[] nums, int target) {
                  for (int i = 0; i < nums.length; i++){
                      for (int k = 0; k < nums.length; k++){
                          if (i != k && nums[i] + nums[k] == target) {
                              first_number = i;
                              second_number = k;
                          }
                      }
                  }
                  return new int[]{first_number, second_number};
                  }
             }
        }

26. Remove Duplicates from Sorted Array
Given an integer array nums sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once. The relative order of the elements should be kept the same.
Consider the number of unique elements in nums to be k​​​​​​​​​​​​​​. After removing duplicates, return the number of unique elements k.
The first k elements of nums should contain the unique numbers in sorted order. The remaining elements beyond index k - 1 can be ignored.

            class Solution {
            public int removeDuplicates(int[] nums) {
                if (nums.length == 0) return 0;
                int slow = 0;
                for (int fast = 1; fast < nums.length; fast++) {
                    if (nums[fast] != nums[slow]){
                        slow++;
                        nums[slow] = nums[fast];
                    }
                }
                return slow + 1;
            }
        }
    
