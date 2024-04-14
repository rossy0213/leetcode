```java
// When we find a element is 1 meaning is part of island.
// Then we use DFS to replace island to '2' to mark it as visisted.
// After we replaced all '1' of a island, then we count up the number of isLand.
// Time complexity: O(N * M) N: number of rows, M: nums of columns
// Space complexity: O(1) No addtioanl memory used here
// Time spend: 04:55
class Solution {
    public int numIslands(char[][] grid) {
        int count = 0;
        for (int y = 0; y < grid.length; y++) {
            for (int x = 0; x < grid[0].length; x++) {
                if (grid[y][x] != '1') {
                    continue;
                }
                fillIsland(grid, x, y);
                count++;
            }
        }

        return count;
    }

    public void fillIsland(char[][] grid, int x, int y) {
        if (y < 0 || y >= grid.length || x < 0 || x >= grid[0].length) {
            return;
        }
        
        if (grid[y][x] != '1') {
            return;
        }
        
        grid[y][x] = '2';

        fillIsland(grid, x + 1, y);
        fillIsland(grid, x - 1, y);
        fillIsland(grid, x, y + 1);
        fillIsland(grid, x, y - 1);
    }
}
```