# Leetcode-2270
# C++ Code

class Solution {
public:
    int waysToSplitArray(vector<int>& nums) {
        long long sum=0;
        for(int i=0;i<nums.size();i++)
        {
            sum+=nums[i];
        }
        long long s=0;
        int count=0;
        for(int i=0;i<nums.size()-1;i++)
        {
            s+=nums[i];
            sum-=nums[i];
            if(s>=sum)count++;
        }
        return count;
    }
};

# Java Code

class Solution {
    public int waysToSplitArray(int[] nums) {
        long totalSum = 0;
        for (int num : nums) {
            totalSum += num;
        }

        int count = 0;
        long leftSum = 0;

        for (int i = 0; i < nums.length - 1; i++) {
            leftSum += nums[i];
            totalSum -= nums[i];
            if (leftSum >= totalSum) {
                count++;
            }
        }

        return count;
    }
}


# Python Code

class Solution:
    def waysToSplitArray(self, nums):
        total_sum = sum(nums)  # Calculate the total sum of the array
        count = 0
        current_sum = 0

        for i in range(len(nums) - 1):
            current_sum += nums[i]
            total_sum -= nums[i]
            if current_sum >= total_sum:
                count += 1

        return count
