```go
// The maximum price that we can reach out is that once we can a number is bigger than previous day
// We buy on the previous day and then sell it
// Time complexity: O(N) N: number of prices
// Space complexity: 1 Only 1 addtional variable here
// Time spend: 01:10
func maxProfit(prices []int) (profit int) {
	for i := 1; i < len(prices); i++ {
		if prices[i] > prices[i - 1] {
			profit += prices[i] - prices[i - 1]
		}
	}

	return
}
```