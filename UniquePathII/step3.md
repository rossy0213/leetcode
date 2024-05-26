```go
// Time spend: 02:02
package main
func uniquePathsWithObstacles(grid [][]int) int {
	dp := make([][]int, len(grid))
	for i := range dp {
		dp[i] = make([]int, len(grid[0]))
	}

	for y := range dp {
		for x := range dp[y] {
			if grid[y][x] == 1 {
				continue
			}

			if x == 0 && y == 0 {
				dp[y][x] = 1
				continue
			}

			if x == 0 {
				dp[y][x] = dp[y - 1][x]
				continue
			}

			if y == 0 {
				dp[y][x] = dp[y][x - 1]
				continue
			}

			dp[y][x] = dp[y - 1][x] + dp[y][x - 1]
		}
	}

	return dp[len(grid) - 1][len(grid[0]) - 1]
}
```

```go
// Time spend: 01:48
package main
func uniquePathsWithObstacles(grid [][]int) int {
	dp := make([][]int, len(grid))
	for i := range dp {
		dp[i] = make([]int, len(grid[0]))
	}

	for y := range dp {
		for x := range dp[y] {
			if grid[y][x] == 1 {
				continue
			}

			if x == 0 && y == 0 {
				dp[y][x] = 1
				continue
			}

			if x == 0 {
				dp[y][x] = dp[y - 1][x]
				continue
			}

			if y == 0 {
				dp[y][x] = dp[y][x - 1]
				continue
			}

			dp[y][x] = dp[y - 1][x] + dp[y][x - 1]
		}
	}

	return dp[len(grid) - 1][len(grid[0]) - 1]
}
```

```go
// Time spend: 01:52
package main
func uniquePathsWithObstacles(grid [][]int) int {
	dp := make([][]int, len(grid))
	for i := range dp {
		dp[i] = make([]int, len(grid[0]))
	}

	for y := range dp {
		for x := range dp[y] {
			if grid[y][x] == 1 {
				continue
			}

			if x == 0 && y == 0 {
				dp[y][x] = 1
				continue
			}

			if x == 0 {
				dp[y][x] = dp[y - 1][x]
				continue
			}

			if y == 0 {
				dp[y][x] = dp[y][x - 1]
				continue
			}

			dp[y][x] = dp[y - 1][x] + dp[y][x - 1]
		}
	}

	return dp[len(grid) - 1][len(grid[0]) - 1]
}
```