```go
// Time spend: 01:07
package main
func uniquePaths(m int, n int) int {
    dp := make([][]int, m)
    for i := range dp {
        dp[i] = make([]int, n)
    }

    for y := range dp {
        for x := range dp[y] {
            if x == 0 || y == 0 {
                dp[y][x] = 1
                continue
            }
            dp[y][x] = dp[y - 1][x] + dp[y][x - 1]
        }
    }

    return dp[m - 1][n - 1]
}
```