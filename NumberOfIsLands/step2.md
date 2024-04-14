```java
// When we find a element is 1 meaning is part of island.
// Then we use DFS to replace island to '2' to mark it as visisted.
// After we replaced all '1' of a island, then we count up the number of isLand.
// Time complexity: O(N * M) N: number of rows, M: nums of columns
// Space complexity: O(1) No addtioanl memory used here
// Time spend: 04:55
class Solution {
    public int numIslands(char[][] grid) {
        if (grid == null || grid.length == 0) {
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

        replaceElementFromSameIsland(grid, x + 1, y);
        replaceElementFromSameIsland(grid, x - 1, y);
        replaceElementFromSameIsland(grid, x, y + 1);
        replaceElementFromSameIsland(grid, x, y - 1);
    }
}
```