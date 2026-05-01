# jump-game-problem

Given an array where each element represents the maximum jump length from that position, determine if you can reach the last index.
Approach
We use a greedy approach to track the maximum reachable index while iterating through the array.

- Initialize maxReach = 0
- For each index:
  - If current index > maxReach → return false
  - Update maxReach = max(maxReach, i + nums[i])
- If maxReach reaches last index → return true

  code:
  class Solution {
    public boolean canJump(int[] nums) {

        int maxReach = 0;

        for (int i = 0; i < nums.length; i++) {

            if (i > maxReach) {
                return false;
            }

            int currentReach = i + nums[i];

            maxReach = Math.max(maxReach, currentReach);

            if (maxReach >= nums.length - 1) {
                return true;
            }
        }

        
        return true;
    }

}
Time: O(n)
Space: O(1)

Dry Run
Input:
nums = [2,3,1,1,4]
Step 1:
dp = [true, false, false, false, false]
Step 2: i = 0 (nums[0] = 2)

👉 yahan se jump kar sakte:

index 1
index 2
dp = [true, true, true, false, false]
Step 3: i = 1 (nums[1] = 3)

👉 jump:

index 2, 3, 4
dp = [true, true, true, true, true]
Step 4:

👉 last index dp[4] = true

✅ Answer = true


Clean and optimized greedy solution with O(n) time complexity.

If you found this helpful, give it a ⭐ and follow for more such solutions 🚀
