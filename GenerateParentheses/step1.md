```java
// Until reach to the max length(n * 2)
// We try to add left part first then add right side
// Until number of left part reach to n, we can add left part
// And if number of left part is bigger than right part, we can try to add right part
// Time complexity: O(2**(N*2)) 
// Space complexity: O(n) stack memory for backtack
// Time spend: XX(Found the answer after checking Solutions tab)
class Solution {
    public List<String> generateParenthesis(int n) {
        List<String> res = new ArrayList<>();
        generateParenthesis(res, 0, 0, "", n);
        return res;
    }

    public void generateParenthesis(List<String> res, int l, int r, String curr,int n) {
        if (curr.length() == n * 2) {
            res.add(curr);
            return;
        }

        if (l < n) {
            generateParenthesis(res, l + 1, r, curr + "(", n);
        }
        if (r < l) {
            generateParenthesis(res, l, r + 1, curr + ")", n);
        }
    }
}
```