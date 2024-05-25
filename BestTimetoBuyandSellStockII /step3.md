```go
// time spend: 00:48
func maxProfit(prices []int) (profit int) {
    for i := 1; i < len(prices); i++ {
        if prices[i] > prices[i - 1] {
            profit += prices[i] - prices[i - 1]
        }
    }

    return
}
```