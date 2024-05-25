```go
// Time spend: 01:00
package main
func maxProfit(prices []int) int {
	buy := -prices[0]
	sell := buy + -prices[0]

	for _, p := range prices {
		buy = max(buy, -p)
		sell = max(sell, buy + p)
	}

	return sell
}

func max(a, b int) int {
	if a > b {
		return a
	}
	return b
}

```

```go
// Time spend: 01:02
package main
func maxProfit(prices []int) int {
	buy := -prices[0]
	sell := buy + -prices[0]

	for _, p := range prices {
		buy = max(buy, -p)
		sell = max(sell, buy + p)
	}

	return sell
}

func max(a, b int) int {
	if a > b {
		return a
	}
	return b
}

```

```go
// Time spend: 00:55
package main
func maxProfit(prices []int) int {
	buy := -prices[0]
	sell := buy + -prices[0]

	for _, p := range prices {
		buy = max(buy, -p)
		sell = max(sell, buy + p)
	}

	return sell
}

func max(a, b int) int {
	if a > b {
		return a
	}
	return b
}

```