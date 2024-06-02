```java
// Time spend: 03:21
class Solution {
    public int shipWithinDays(int[] weights, int days) {
        int l = -1;
        int r = 0;
        for (int weight : weights) {
            if (weight > l) {
                l = weight;
            }
            r += weight;
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
        int daysNeed = 1;
        int currWeight = 0;
        for (int weight : weights) {
            if (currWeight + weight > cap) {
                daysNeed++;
                if (daysNeed > days) {
                    return false;
                }
                currWeight = 0;
            }
            currWeight += weight;
        }

        return true;
    }
}
```