```java
// When we find 1 in the element, we use DFS to all '1' for the same isLand and count the size of isLand.
// Then we compare the size of the island that we find to pick the biggest one.
// Time complexity: O(M*N) M: number of rows, N: number of columns
// Space complexity: O(M*N)
// Time spend: 15:30
class Solution {
    public int maxAreaOfIsland(int[][] grid) {
        int max = 0;
        for (int y = 0; y < grid.length; y++) {
            for (int x = 0; x < grid[0].length; x++) {
                if (grid[y][x] == 1) {
                    int size = findSizeOfIsland(grid, x, y);
                    max = Math.max(max, size);
                } 
            }
        }

        return max;
    }

    public int findSizeOfIsland(int[][] grid, int x, int y) {
        if (y < 0 || y >= grid.length || x < 0 || x >= grid[0].length || grid[y][x] != 1) {
            return 0;
        }
        
        grid[y][x] = 2;
        return 1 + findSizeOfIsland(grid, x + 1, y) + findSizeOfIsland(grid, x - 1, y) + findSizeOfIsland(grid, x, y + 1) + findSizeOfIsland(grid, x, y - 1);
    }
}
```