```java
// Time spend: 03:31
class Solution {
    public int numIslands(char[][] grid) {
        if (grid == null || grid.length == 0 || grid[0].length == 0) {
            return 0;
        }

        int cnt = 0;
        for (int y = 0; y < grid.length; y++) {
            for (int x = 0; x < grid[0].length; x++) {
                if (grid[y][x] == '1') {
                    replaceElementFromSameIsland(grid, x, y);
                    cnt++;
                }
            }
        }

        return cnt;
    }

    public void replaceElementFromSameIsland(char[][] grid, int x, int y) {
        if (y < 0 || y >= grid.length || x < 0 || x >= grid[0].length || grid[y][x] != '1') {
            return;
        }

        grid[y][x] = '2';
        replaceElementFromSameIsland(grid, x - 1, y);
        replaceElementFromSameIsland(grid, x + 1, y);
        replaceElementFromSameIsland(grid, x, y - 1);
        replaceElementFromSameIsland(grid, x, y + 1);
    }
}
```

```java
// Time spend: 03:15
class Solution {
    public int numIslands(char[][] grid) {
        if (grid == null || grid.length == 0) {
            return 0;
        }

        int cnt = 0;
        for (int y = 0; y < grid.length; y++) {
            for (int x = 0; x < grid[0].length; x++) {
                if (grid[y][x] == '1') {
                    findBoundariesOfIsland(grid, x, y);
                    cnt++;
                }
            }
        }

        return cnt;
    }

    public void findBoundariesOfIsland(char[][] grid, int x, int y) {
        if (y >= 0 && y < grid.length && x >= 0 && x < grid[0].length && grid[y][x] == '1') {
            grid[y][x] = '2';
            findBoundariesOfIsland(grid, x - 1, y);
            findBoundariesOfIsland(grid, x + 1, y);
            findBoundariesOfIsland(grid, x, y - 1);
            findBoundariesOfIsland(grid, x, y + 1);
        }
    }
}
```

```java
// Time spend: 02:50
class Solution {
    public int numIslands(char[][] grid) {
        if (grid == null || grid.length == 0 || grid[0].length == 0) {
            return 0;
        }

        int cnt = 0;
        for (int y = 0; y < grid.length; y++) {
            for (int x = 0; x < grid[0].length; x++) {
                if (grid[y][x] == '1') {
                    replaceElementFromSameIsland(grid, x, y);
                    cnt++;
                }
            }
        }

        return cnt;
    }

    public void replaceElementFromSameIsland(char[][] grid, int x, int y) {
        if (y < 0 || y >= grid.length || x < 0 || x >= grid[0].length || grid[y][x] != '1') {
            return;
        }

        grid[y][x] = '2';
        replaceElementFromSameIsland(grid, x - 1, y);
        replaceElementFromSameIsland(grid, x + 1, y);
        replaceElementFromSameIsland(grid, x, y - 1);
        replaceElementFromSameIsland(grid, x, y + 1);
    }
}
```