```go
// Time spend: 01:10
func maxProfit(prices []int) int {
	buy := -prices[0]
	sell := buy + prices[0]

	for _, p := range prices {
		buy = max(buy, -p)
		sell = max(sell, buy + p)
	}

	return sell
}

func max(a, b int) int {
	if a < b {
		return b
	}
	return a
}
```