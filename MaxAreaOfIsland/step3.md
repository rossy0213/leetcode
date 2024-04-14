```java
// Time spend: 03:32
class Solution {
    public int maxAreaOfIsland(int[][] grid) {
        int biggestIslandSize = 0;

        for (int y = 0; y < grid.length; y++) {
            for (int x = 0; x < grid[0].length; x++) {
                if (grid[y][x] == 1) {
                    int islandSize = findIslandSize(grid, x, y);
                    biggestIslandSize = Math.max(biggestIslandSize, islandSize);
                }
            }
        }

        return biggestIslandSize;
    }

    public int findIslandSize(int[][] grid, int x, int y) {
        if (y < 0 || y >= grid.length || x < 0 || x >= grid[0].length) {
            return 0;
        }

        if (grid[y][x] != 1) {
            return 0;
        }

        grid[y][x] = 2;
        return 1 + findIslandSize(grid, x - 1, y)
                + findIslandSize(grid, x + 1, y)
                + findIslandSize(grid, x, y + 1)
                + findIslandSize(grid, x, y - 1);
    }
}
```

```java
// Time spend: 03:36
class Solution {
    public int maxAreaOfIsland(int[][] grid) {
        int biggestIslandSize = 0;

        for (int y = 0; y < grid.length; y++) {
            for (int x = 0; x < grid[0].length; x++) {
                if (grid[y][x] == 1) {
                    int islandSize = findIslandSize(grid, x, y);
                    biggestIslandSize = Math.max(biggestIslandSize, islandSize);
                }
            }
        }

        return biggestIslandSize;
    }

    public int findIslandSize(int[][] grid, int x, int y) {
        if (y < 0 || y >= grid.length || x < 0 || x >= grid[0].length) {
            return 0;
        }

        if (grid[y][x] != 1) {
            return 0;
        }

        grid[y][x] = 2;
        return 1 + findIslandSize(grid, x - 1, y)
                + findIslandSize(grid, x + 1, y)
                + findIslandSize(grid, x, y - 1)
                + findIslandSize(grid, x, y + 1);
    }
}
```

```java
// Time spend: 03:59
class Solution {
    public int maxAreaOfIsland(int[][] grid) {
        int biggestIslandSize = 0;

        for (int y = 0; y < grid.length; y++) {
            for (int x = 0; x < grid[0].length; x++) {
                if (grid[y][x] == 1) {
                    int islandSize = findIslandSize(grid, x, y);
                    biggestIslandSize = Math.max(biggestIslandSize, islandSize);
                }
            }
        }

        return biggestIslandSize;
    }

    public int findIslandSize(int[][] grid, int x, int y) {
        if (y < 0 || y >= grid.length || x < 0 || x >= grid[0].length) {
            return 0;
        }

        if (grid[y][x] != 1) {
            return 0;
        }

        grid[y][x] = 2;
        return 1 + findIslandSize(grid, x - 1, y)
                + findIslandSize(grid, x + 1, y)
                + findIslandSize(grid, x, y + 1)
                + findIslandSize(grid, x, y - 1);
    }
}
```