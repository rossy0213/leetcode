```java
// Using binary search to find the minimum cap that we can ship the packages
// Min(left) will be the max value in the array, Max(right) will be sum of the values(when we need to ship everything in a day)
// During the search, if we can ship it meaning the smallest cap in left ~ mid 
// if we can't, meaning we need to search between mid + 1 ~ right
// Time complexity: O(NlogM) -> N: number of weights, M: sum of values - max value  
// Space complexity: O(1)
// Time spend: 08:34
class Solution {
    public int shipWithinDays(int[] weights, int days) {
        int l = -1;
        int r = 0;
        for (int w : weights) {
            if (w > l) {
                l = w;
            }
            r += w;
        }

        while (l < r) {
            int mid = (l + r) / 2;
            if (canShip(weights, mid, days)) {
                r = mid;
            } else {
                l = mid + 1;
            }
        }

        return l;
    }

    public boolean canShip(int[] weights, int cap, int days) {
        int day = 1;
        int temp = 0;
        for (int w : weights) {
            if (temp + w <= cap) {
                temp += w;
                continue;
            }
            day++;
            if (day > days) {
                return false;
            }
            temp = w;
        }

        return true;
    }
}
```