# Leetcode----2918
Minimum Equal Sum of Two arrays after replacing Zeros
//code in java 
class Solution {
    public long minSum(int[] nums1, int[] nums2) {
        long sum1 = 0, sum2 = 0;
        int zeros1 = 0, zeros2 = 0;

        for (int num : nums1) {
            if (num == 0) {
                zeros1++;
            } else {
                sum1 += num;
            }
        }

        for (int num : nums2) {
            if (num == 0) {
                zeros2++;
            } else {
                sum2 += num;
            }
        }

        if (sum1 + zeros1 > sum2 + zeros2) {
            if (zeros2 == 0) return -1;
            return sum1 + zeros1;
        } else if (sum2 + zeros2 > sum1 + zeros1) {
            if (zeros1 == 0) return -1;
            return sum2 + zeros2;
        } else {
             return sum1 + zeros1;
        }
    }
}
