```go
// Use DP
// When x == 0 or y == 0 the number of path will be 1
// Other than that, the number of path will be dp[y][x - 1] + dp[y - 1][x]
// Time complexity: O(M * n)
// Space complexity: O(M * N)
// Time spend: 03:14
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