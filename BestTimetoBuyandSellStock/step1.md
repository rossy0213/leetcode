```go
// For each day, 
// We need to check if it's day that we can buy the stock with lower price
// And then check what if we sell it with the lowest price that we found in the past
// Time complexity:  O(N) N: number of prices
// Space complexity: 1
// Time spend: 04:32
func maxProfit(prices []int) int {
    buy := -prices[0];
    sell := buy + prices[0];

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