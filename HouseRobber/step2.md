```go 
// Time spend: 01:12
package main
func rob(nums []int) int {
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