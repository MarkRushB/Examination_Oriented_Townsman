# Fresh Promotion

Amazon is running a promotion in which customers receive prizes for purchasing a secret combination of fruits. The combination will change each day, and the team running the promotion wants to use a code list to make it easy to change the combination. The code list contains groups of fruits. Both the order of the groups within the code list and the order of the fruits within the groups matter. However, between the groups of fruits, any number, and type of fruit is allowable. The term "anything" is used to allow for any type of fruit to appear in that location within the group.

Consider the following secret code list: `[[apple, apple], [banana, anything, banana]]`
Based on the above secret code list, a customer who made either of the following purchases would win the prize:
orange, apple, apple, banana, orange, banana
apple, apple, orange, orange, banana, apple, banana, banana

Write an algorithm to output 1 if the customer is a winner else output 0.

```java
private static int freshPromotion( String[] shoppingCart, String[][] codeList){
    if(codeList.length == 0) return 1;
    if(codeList[0].length == 0) return 1;
    int cart = 0;
    int code = 0;
    while(cart < shoppingCart.length && code < codeList.length){
        String cur = shoppingCart[cart];
        if((codeList[code][0].equalsIgnoreCase(cur) || codeList[code][0].equalsIgnoreCase("anything")) && check(codeList[code], shoppingCart, cart)){
            cart += codeList[code++].length;
        }else{
            cart++;
        }
    }
    return code == codeList.length ? 1 : 0;
}
private static boolean check(String[] code, String[] cart, int index){
    for(String s : code){
        if( index < cart.length && (s.equalsIgnoreCase(cart[index]) || s.equalsIgnoreCase("anything"))){
            index++;
        }else{
            return false;
        }
    }
    return true;
}
```

# Amazon Fulfillment Builder

![](https://assets.leetcode.com/users/images/3f25d8e5-66a7-41ab-a079-bb4f928a0168_1622052285.1791687.jpeg)
![](https://assets.leetcode.com/users/images/5a57b50b-6d6c-4c76-a48a-b7c6e2a184d9_1622052296.5088093.jpeg)

```java
class Solution {
    public int connectSticks(int[] sticks) {
        int totalSum = 0;
        PriorityQueue<Integer> pq = new PriorityQueue<>();
        for(int item : sticks){
            pq.offer(item);
        }
        while(pq.size() > 1){
            int curCost = pq.poll() + pq.poll();
            totalSum += curCost;
            pq.offer(curCost);
        }
        return totalSum;
    }
}
```

List 1: 40 problems
List 2:
List 3:

# [1. Two Sum](https://leetcode.com/problems/two-sum/)

Use a hashset, for index, use a hashmap

# [8. String to Integer (atoi)](https://leetcode.com/problems/string-to-integer-atoi/)

 First judge whether it is out of bounds, and then deal with it
```java
class Solution {
    public int myAtoi(String s) {
        int len = s.length();
        char[] c = s.toCharArray();
        int index = 0;
        while(index < len && c[index] == ' '){
            index++;
        }
        if(index == len) return 0;
        int sign = 1;
        if(c[index] == '+'){
            index++;
        }else if(c[index] == '-'){
            sign = -1;
            index++;
        }
        int res = 0;
        while(index < len && c[index] <= '9' && c[index] >= '0'){
            char cur = c[index];
            if(res > Integer.MAX_VALUE / 10 || (res == Integer.MAX_VALUE / 10 && cur - '0' > Integer.MAX_VALUE % 10)){
                return Integer.MAX_VALUE;
            }
            if(res < Integer.MIN_VALUE / 10 || (res == Integer.MIN_VALUE / 10 && cur - '0' > -(Integer.MIN_VALUE % 10))){
                return Integer.MIN_VALUE;
            }
            res = res * 10 + sign * (cur - '0');
            index++;
        }
        return res;
    }
}
```
# [12. Integer to Roman](https://leetcode.com/problems/integer-to-roman/)

**GREEDY ALGORITHM**

1. list all the situation, 1, 5, 10, 50, 100, 500, 1000 is the key number, 4, 9, 40, 90, 400, 900 is also the key number we need to do substraction
2. then use greedy to scan the number from head to tail
```java
class Solution {
    public String intToRoman(int num) {
        int[] nums = {1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1};
        String[] roman = {"M", "CM", "D", "CD", "C", "XC", "L", "XL", "X", "IX", "V", "IV", "I"};
        StringBuilder sb = new StringBuilder();
        int index = 0;
        
        // num = 3491, 2491, 1491, 491, 91
        // index = 0
        // MMMCDXCI
        
        while(index < 13){
            while(num >= nums[index]){
                sb.append(roman[index]);
                num -= nums[index];
            }
            index++;
        }
        return sb.toString();
    }
}
```

# [13. Roman to Integer](https://leetcode.com/problems/roman-to-integer/)

Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.

    Symbol       Value
    I             1
    V             5
    X             10
    L             50
    C             100
    D             500
    M             1000
For example, 2 is written as II in Roman numeral, just two one's added together. 12 is written as XII, which is simply X + II. The number 27 is written as XXVII, which is XX + V + II.

Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not IIII. Instead, the number four is written as IV. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as IX. There are six instances where subtraction is used:

- I can be placed before V (5) and X (10) to make 4 and 9. 
- X can be placed before L (50) and C (100) to make 40 and 90. 
- C can be placed before D (500) and M (1000) to make 400 and 900.

Given a roman numeral, convert it to an integer.

```java
class Solution {
    public int romanToInt(String s) {
        Map<Character, Integer> map = new HashMap<>();
        map.put('I', 1);
        map.put('V', 5);
        map.put('X', 10);
        map.put('L', 50);
        map.put('C', 100);
        map.put('D', 500);
        map.put('M', 1000);
        
        int res = 0;
        int max = 1;
        for(int i = s.length() - 1; i >= 0; i--){
            int cur = map.get(s.charAt(i));
            if(cur >= max){
                res += cur;
                max = cur
            }else{
                res -= cur;
            }
        }
        return res;
    }
}
```

# [20. Valid Parentheses](https://leetcode.com/problems/valid-parentheses/)

Stack to opreate, meet ( add ), meet [ add ], meet { add }, remember to determine that at the end, if the deque isEmpty();

```java
class Solution {
    public boolean isValid(String s) {
        Deque<Character> deque = new ArrayDeque<>();
        for(char c : s.toCharArray()){
            if(c == '('){
                deque.addLast(')');
            }else if(c == '['){
                deque.addLast(']');
            }else if(c == '{'){
                deque.addLast('}');
            }else if(deque.isEmpty() || c != deque.removeLast()){
                return false;
            }
        }
        return deque.isEmpty();
    }
}
```

# [23. Merge k Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists/)

You are given an array of `k` linked-lists `lists`, each linked-list is sorted in ascending order.

Merge all the linked-lists into one sorted linked-list and return it.

**Example 1:**

    Input: lists = [[1,4,5],[1,3,4],[2,6]]
    Output: [1,1,2,3,4,4,5,6]
    Explanation: The linked-lists are:
    [
        1->4->5,
        1->3->4,
        2->6
    ]
    merging them into one sorted list:
    1->1->2->3->4->4->5->6

    
**USE PRIORITQUEUE**

先把list中每个头节点放进pq里面，然后拿出来接到cur后面，然后cur = cur.next， 然后将当前cur的next丢进pq里面维护整个pq

注意一开始放进去的时候，要判断当前ListNode为不为空
    
O(nlogK)

```java
class Solution {
    public ListNode mergeKLists(ListNode[] lists) {
        PriorityQueue<ListNode> pq = new PriorityQueue<>((a, b) -> a.val - b.val);
        for(ListNode list : lists){
            if(list != null)
                pq.offer(list);
        }
        
        ListNode dummy = new ListNode(0);
        ListNode cur = dummy;
        while(!pq.isEmpty()){
            cur.next = pq.poll();
            cur = cur.next;
            if(cur.next != null){
                pq.offer(cur.next);
            }
        }
        return dummy.next;
    }
}
```

# [36. Valid Sudoku](https://leetcode.com/problems/valid-sudoku/)

i / 3, j / 3 reprent box coordinate

```java
class Solution {
    public boolean isValidSudoku(char[][] board) {
        boolean[][] row = new boolean[9][9];
        boolean[][] col = new boolean[9][9];
        boolean[][][] box = new boolean[3][3][9];
        
        for(int i = 0; i < 9; i++){
            for(int j = 0; j < 9; j++){
                if(board[i][j] != '.'){
                    int cur = board[i][j] - '1';
                    if(row[i][cur] || col[j][cur] || box[i / 3][j / 3][cur]){
                        return false;
                    }else{
                        row[i][cur] = true;
                        col[j][cur] = true;
                        box[i / 3][j / 3][cur] = true; 
                    }
                }
            }
        }
        return true;
    }
}
```

# [39. Combination Sum](https://leetcode.com/problems/combination-sum/)

看我的leetcode practice，有详细讲解
```java
class Solution {
    Deque<Integer> path = new ArrayDeque<>();
    List<List<Integer>> res = new ArrayList<>();
    int sum = 0;
    public List<List<Integer>> combinationSum(int[] candidates, int target) {
        if(candidates == null || candidates.length == 0) return res;
        help(candidates, target, 0);
        return res;
    }
    private void help(int[] candidates, int target, int start){
        if(sum == target){
            res.add(new ArrayList<>(path));
            return;
        }
        if(sum > target) return;
        for(int i = start; i < candidates.length; i++){
            path.addLast(candidates[i]);
            sum += candidates[i];
            help(candidates, target, i);
            sum -= candidates[i];
            path.removeLast();
        }
    }
}
```
# [46. Permutations](https://leetcode.com/problems/permutations/)

看我的leetcode practice，有详细讲解
要弄清permutation和combination的区别，一个是顺序不一样但重复也是可以的，一个是完全不能重复，这就决定了在回溯的过程中是使用start变量还是用boolean[]数组来判断是否访问过。

因为permutations是不允许重复的，也就意味着[1, 2, 3] 和 [1, 3, 2]是一样的，所以我们要使用boolean数组来判断当前元素有没有使用过。

但是combination是可以允许重复的元素的，比如[2, 2, 3] 这样也是可以的，所以在这里我们就使用start变量来记录，其中如果不让使用当前元素的话，我们下次recursion开始就要从start + 1, 这样可以避免重复。

```java
class Solution {
    List<List<Integer>> res = new ArrayList<>();
    Deque<Integer> path = new ArrayDeque<>();
    boolean[] used;
    public List<List<Integer>> permute(int[] nums) {
        used = new boolean[nums.length];
        if(nums == null || nums.length == 0) return res;
        help(nums);
        return res;
    }
    private void help(int[] nums){
        if(path.size() == nums.length){
            res.add(new ArrayList<>(path));
            return;
        }
        for(int i = 0; i < nums.length; i++){
            if(!used[i]){
                path.addLast(nums[i]);
                used[i] = true;
                help(nums);
                used[i] = false;
                path.removeLast();
            }
        }
    }
}
```

# [211. Design Add and Search Words Data Structure](https://leetcode.com/problems/design-add-and-search-words-data-structure/)
```java
class WordDictionary {

    /** Initialize your data structure here. */
    TrieNode root;
    public WordDictionary() {
        root = new TrieNode();
    }
    
    public void addWord(String word) {
        TrieNode node = root;
        for(char c : word.toCharArray()){
            if(node.children[c - 'a'] == null){
                node.children[c - 'a'] = new TrieNode();
            }
            node = node.children[c - 'a'];
        }
        node.isWord = true;
    }
    
    public boolean search(String word) {
        return helper(word, 0, root);
    }
    public boolean helper(String word, int pos, TrieNode node){
        if(pos == word.length()){
            return node.isWord;
        }
        char c = word.charAt(pos);
        if(c != '.'){
            return node.children[c - 'a'] != null && helper(word, pos + 1, node.children[c - 'a']);
        }
        for(int i = 0; i < 26; i++){
            if(node.children[i] != null && helper(word, pos + 1, node.children[i])){
                return true;
            }
        }
        return false;
    }
}
class TrieNode{
    boolean isWord;
    TrieNode[] children;
    public TrieNode(){
        children = new TrieNode[26];
    }
}

/**
 * Your WordDictionary object will be instantiated and called as such:
 * WordDictionary obj = new WordDictionary();
 * obj.addWord(word);
 * boolean param_2 = obj.search(word);
 */
```
# [212. Word Search II](https://leetcode.com/problems/word-search-ii/)
```java
class Solution {
    int m;
    int n;
    int[][] dir = {{1, 0},{-1, 0},{0 ,1},{0, -1}};
    List<String> res;
    public List<String> findWords(char[][] board, String[] words) {
        m = board.length;
        n = board[0].length;
        res = new ArrayList<>();
        TrieNode root = new TrieNode();
        buildTrie(root, words);
        for(int i = 0; i < m; i++){
            for(int j = 0; j < n; j++){
                char c = board[i][j];
                if(root.children[c - 'a'] != null){
                    dfs(board, i, j, root);
                }
            }
        }
        return res;
    }
    private void buildTrie(TrieNode root, String[] words){
        for(String s : words){
            TrieNode node = root;
            for(char c : s.toCharArray()){
                if(node.children[c - 'a'] == null){
                    node.children[c - 'a'] = new TrieNode();
                }
                node = node.children[c - 'a'];
            }
            node.word = s;
        }
    }
    private void dfs(char[][] board, int x, int y, TrieNode node){
        if(x < 0 || x > m - 1 || y < 0 || y > n - 1){
            return;
        }
        char c = board[x][y];
        if(c == '*' || node.children[c - 'a'] == null){
            return;
        }
        node = node.children[c - 'a'];
        if(node.word != null){
            res.add(node.word);
            node.word = null;
        }
        board[x][y] = '*';
        for(int[] d : dir){
            int nx = d[0] + x;
            int ny = d[1] + y;
            dfs(board, nx, ny, node);
        }
        board[x][y] = c;
    }
}
class TrieNode{
    TrieNode[] children;
    String word;
    public TrieNode(){
        children = new TrieNode[26];
    }
}
```

# 348 Design Tic-Tac-Toe 
```java
class TicTacToe{
    int[][] rows;
    int[][] cols;
    int[] diag;
    int[] adiag;
    int size;
    public TicTacToe(int n){
        rows = new int[n][2];
        cols = new int[n][2];
        diag = new int[2];
        adiag = new int[2];
        size = n;

    }
    public int move(int col, int row, int player){
        rows[row][player - 1]++;
        if(rows[row][player - 1] == size) return player;
        cols[col][player - 1]++;
        if(cols[col][player - 1] == size) return player;
        if(row == col){
            diag[player - 1]++;
            if(diag[player - 1] == size) return player;
        }
        if(row + col = size - 1){
            adiag[player - 1]++;
            if(adiag[player - 1] == size) return player;
        }
        return 0;
    }
}
```

# 417. Pacific Atlantic Water Flow

```java
class Solution {
    int m;
    int n;
    List<List<Integer>> res;
    boolean[][] meet;
    boolean[][] vis;
    int[][] dir = {{1, 0},{-1, 0},{0, 1},{0, -1}};
    public List<List<Integer>> pacificAtlantic(int[][] heights) {
        m = heights.length;
        n = heights[0].length;
        res = new ArrayList<>();
        meet = new boolean[m][n];
        vis = new boolean[m][n];
        for(int i = 0; i < m; i++){
            for(int j = 0; j < n; j++){
                if((i == 0 || j == 0) && !vis[i][j]){
                    help(heights, i, j, false);
                }
            }
        }
        vis = new boolean[m][n];
        for(int i = 0; i < m; i++){
            for(int j = 0; j < n; j++){
                if((i ==  m - 1 || j == n -1) && !vis[i][j]){
                    help(heights, i, j, true);
                }
            }
        }
        return res;
    }
    private void help(int[][] heights, int x, int y, boolean isA){
        if(isA && meet[x][y]){
            List<Integer> cur = Arrays.asList(x, y);
            res.add(cur);
            meet[x][y] = false;
        }
        if(!isA) meet[x][y] = true;
        for(int[] d : dir){
            int nx = d[0] + x;
            int ny = d[1] + y;
            if(nx >= 0 && nx < m && ny >= 0 && ny < n && !vis[nx][ny] && heights[nx][ny] >= heights[x][y]){
                vis[nx][ny] = true;
                help(heights, nx, ny, isA);
            }
        }
    }
}
```