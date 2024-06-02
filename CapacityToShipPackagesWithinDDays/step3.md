```java
// Time spend: 03:11
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
                continue;
            }
            l = mid + 1;
        }

        return l;
    }

    public boolean canShip(int[] weights, int cap, int days) {
        int daysNeed = 1;
        int currWeight = 0;
        for (int weight : weights) {
            if (currWeight + weight > cap) {
                currWeight = 0;
                daysNeed++;
                if (daysNeed > days) {
                    return false;
                }
            }
            currWeight += weight;
        }

        return true;
    }
}
```

```java
// Time spend: 02:47
class Solution {
    public int shipWithinDays(int[] weights, int days) {
        int l = -1;
        int r = 0;
        for (int w : weights) {
            l = Math.max(w, l);
            r += w;
        }

        while (l < r) {
            int mid = (l + r) / 2;
            if (canShip(weights, days, mid)) {
                r = mid;
                continue;
            }
            l = mid + 1;
        }

        return l;
    }

    public boolean canShip(int[] weights, int days, int cap) {
        int daysNeed = 1;
        int currWeight = 0;
        for (int w : weights) {
            if (currWeight + w > cap) {
                currWeight = 0;
                daysNeed++;
                if (daysNeed > days) {
                    return false;
                }
            }
            currWeight += w;
        }

        return true;
    }
}
```

```java
// Time spend: 02:21
class Solution {
    public int shipWithinDays(int[] weights, int days) {
        int l = -1;
        int r = 0;
        for (int w : weights) {
            l = Math.max(l, w);
            r += w;
        }

        while (l < r) {
            int mid = (l + r) / 2;
            if (canShip(weights, days, mid)) {
                r = mid;
                continue;
            }
            l = mid + 1;
        }

        return l;
    }

    public boolean canShip(int[] weights, int days, int cap) {
        int daysNeed = 1;
        int currWeight = 0;
        for (int w : weights) {
            if (currWeight + w > cap) {
                currWeight = 0;
                daysNeed++;
                if (daysNeed > days) {
                    return false;
                }
            }
            currWeight += w;
        }

        return true;
    }
}
```