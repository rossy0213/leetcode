```java
// Time spend: 01:33
class Solution {
    public List<String> generateParenthesis(int n) {
        List<String> res = new ArrayList<>();
        generateParenthesis(res, 0, 0, n, "");
        return res;
    }

    public void generateParenthesis(List<String> res, int l, int r, int n, String curr) {
        if (curr.length() == n * 2) {
            res.add(curr);
            return;
        }

        if (l < n) {
            generateParenthesis(res, l + 1, r, n, curr + '(');
        }

        if (r < l) {
            generateParenthesis(res, l, r + 1, n, curr + ')');
        }
    }
}
```

```java
// Time spend: 01:37
class Solution {
    public List<String> generateParenthesis(int n) {
        List<String> res = new ArrayList<>();
        generateParenthesis(res, 0, 0, n, "");
        return res;
    }

    public void generateParenthesis(List<String> res, int l, int r, int n, String curr) {
        if (curr.length() == n * 2) {
            res.add(curr);
            return;
        }

        if (l < n) {
            generateParenthesis(res, l + 1, r, n, curr + '(');
        }

        if (r < l) {
            generateParenthesis(res, l, r + 1, n, curr + ')');
        }
    }
}
```

```java
// Time spend: 01:26
class Solution {
    public List<String> generateParenthesis(int n) {
        List<String> res = new ArrayList<>();
        generateParenthesis(res, 0, 0, n, "");
        return res;
    }

    public void generateParenthesis(List<String> res, int l, int r, int n, String curr) {
        if (curr.length() == n * 2) {
            res.add(curr);
            return;
        }

        if (l < n) {
            generateParenthesis(res, l + 1, r, n, curr + '(');
        }

        if (r < l) {
            generateParenthesis(res, l, r + 1, n, curr + ')');
        }
    }
}
```