```go
// DP
// Thought there is a cycle of hourse
// We need to break it to two parts, one it's remove the first house and the another remove the last house
// Since those two house it connected
// We need to keep two array of DP to track the num that we can reach
// Time complexity: O(N) N: number of given nums
// Space complexity: O(N) 
// Time spend: 03:49
package main
func rob(nums []int) int {
    if len(nums) == 1 {
        return nums[0]
    }

    return max(robHouses(nums[1:]), robHouses(nums[:len(nums) - 1]))
}

func robHouses(nums []int) int {
    dp := make([]int, len(nums) + 2)
    
    for i := 2; i < len(dp); i++ {
        dp[i] = max(dp[i - 2] + nums[i - 2], dp[i - 1])
    }

    return dp[len(dp) - 1]
}

func max(a, b int) int {
    if a > b {
        return a
    }

    return b
}
```