```go
// DP
// If there is stone(1) in the gird, meaning path is 0 since we have no way to reach
// Also since there is only 1 way for the first column and first row, so only we find a stone in
// there, meaning we also can reach to the rest places.
// Time complexity: O(M * N)
// Space complexity: O(M * N)
// Time spend: 08:24
package main
func uniquePathsWithObstacles(grid [][]int) int {
    dp := make([][]int, len(grid))
    for i := range dp {
        dp[i] = make([]int, len(grid[0]))
    }
    
    for y := 0; y < len(dp); y++ {
        for x := 0; x < len(dp[y]); x++ {
            if grid[y][x] == 1 {
                continue
            }
            if x == 0 || y == 0 {
                if (y > 0 && dp[y - 1][x] == 0) || x > 0 && dp[y][x - 1] == 0 {
                    dp[y][x] = 0
                    continue
                } 
                dp[y][x] = 1
                continue
            }
            dp[y][x] = dp[y - 1][x] + dp[y][x - 1]
        }
    }

    return dp[len(grid) - 1][len(grid[0]) - 1]
}
```