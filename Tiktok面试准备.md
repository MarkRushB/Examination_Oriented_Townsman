## [33 Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/)
```java
class Solution {
    public int search(int[] nums, int target) {
        int left = 0;
        int right = nums.length - 1;
        while(left <= right){
            int mid = left + (right - left) / 2;
            if(nums[mid] == target){
                return mid;
            }
            if(nums[mid] >= nums[left]){
                if(nums[left] <= target && target <= nums[mid]){
                    right = mid;
                }else{
                    left = mid + 1;
                }
            }else{
                if(nums[mid] <=  target && target <= nums[right]){
                    left = mid;
                }else{
                    right = mid - 1;
                }
            }
        }
        return -1;
    }
}
```
- 因为是找某个index -> `while(left <= right)`
- `if(nums[mid] >= nums[left])`这里的 = 是因为数组可能只有两个元素，所以mid有可能等于left
- `if(nums[left] <= target && target <= nums[mid])`当target落在前半部分的单调区间里的时候，因为target <= nums[mid]， 所以mid也可能是我们要找的目标，所以下次right = mid，而else里面的，既然mid属于单调区间，我们就需要将left = mid + 1

## [98 Validate Binary Search Tree](https://leetcode.com/problems/validate-binary-search-tree/)
- 没什么说的，记住就完事了

## [1375 Number of Times Binary String Is Prefix-Aligned](https://leetcode.com/problems/number-of-times-binary-string-is-prefix-aligned/)
- 这个题也以红绿灯的问题出现过，换汤不换药
- 核心思路：遍历flips array，并且记录当前翻转过的最大下标，然后与已翻转过的数量进行比较，如果相等，那么就是valide

## [480. Sliding Window Median](https://leetcode.com/problems/sliding-window-median/)
```java
class Solution {
    public double[] medianSlidingWindow(int[] nums, int k) {
        int n = nums.length;
        int cnt = n - k + 1;
        double[] res = new double[cnt];
        PriorityQueue<Integer> left = new PriorityQueue<>((a, b) -> Integer.compare(b, a));
        PriorityQueue<Integer> right = new PriorityQueue<>((a, b) -> Integer.compare(a, b));
        for(int i = 0; i < k; i++){
            right.offer(nums[i]);
        }
        for(int i = 0; i < k / 2; i++){
            left.offer(right.poll());
        }
        res[0] = getMid(left, right);
        for(int i = k; i < n; i++){
            int add = nums[i];
            int del = nums[i - k];
            if(add >= right.peek()){
                right.offer(add);
            }else{
                left.offer(add);
            }
            if(del >= right.peek()){
                right.remove(del);
            }else{
                left.remove(del);
            }
            adjust(left, right);
            res[i - k + 1] = getMid(left, right);
        }
        return res;
    }
    private void adjust(PriorityQueue<Integer> left, PriorityQueue<Integer> right){
        while(left.size() > right.size()){
            right.add(left.poll());
        }
        while(right.size() - left.size() > 1){
            left.add(right.poll());
        }
    }
    private double getMid(PriorityQueue<Integer> left, PriorityQueue<Integer> right){
        if(left.size() == right.size()){
            return (left.peek() / 2.0) + (right.peek() / 2.0);
        }else{
            return right.peek() * 1.0;
        }
    }
}
```
- 核心思路，用大顶堆和小顶堆来做，思路就是小顶堆存右半部分，大顶堆存左半部分，要注意始终保持right.size() = left.size() 或者 right.size() - left.size() = 1

## [702. Search in a Sorted Array of Unknown Size](https://leetcode.com/problems/search-in-a-sorted-array-of-unknown-size/)
- 先left = 0， right = 1， 然后 right *= 2往右扩张边界，同时更新left = right，这样可以很快找到一个target在的区间，然后再进行binary search

## [204. Count Primes](https://leetcode.com/problems/count-primes/)
```java
class Solution {
    public int countPrimes(int n) {
        boolean[] isP = new boolean[n];
        Arrays.fill(isP, true);
        for(int i = 2; i * i < n; i++){
            if(isP[i]){
                for(int j = i * i; j < n; j += i){
                    isP[j] = false;
                }
            }
        }
        int res = 0;
        for(int i = 2; i < n; i++){
            if(isP[i]) res++;
        }
        return res;
    }
}
```
## [528. Random Pick with Weight](https://leetcode.com/problems/random-pick-with-weight/)
```java
class Solution {
    int[] sum;
    public Solution(int[] w) {
        int n = w.length;
        sum = new int[n + 1];
        for(int i = 1; i <= n; i++){
            sum[i] = w[i - 1] + sum[i - 1];
        }
    }
    
    public int pickIndex() {
        int n = sum.length;
        int t = (int)(Math.random() * sum[n - 1]) + 1;
        int left = 1; 
        int right = n - 1;
        while(left < right){
            int mid = left + (right - left) / 2;
            if(sum[mid] >= t){
                right = mid;
            }else{
                left = mid + 1;
            }
        }
        return left - 1;
    }
}
```
- 想像成一条线段，然后随机生成一个数去在线段上找，这个[解析](https://leetcode-cn.com/problems/random-pick-with-weight/solution/tu-jie-an-quan-zhong-sui-ji-xuan-ze-zhi-pu1mv/)很棒

## [855. Exam Room](https://leetcode.com/problems/exam-room/)
```java
class ExamRoom {
    int n;
    TreeSet<Integer> students;
    public ExamRoom(int n) {
        this.n = n;
        students = new TreeSet<>();
    }
    
    public int seat() {
        int student = 0;
        if(students.size() > 0){
            int dist = students.first();
            Integer prev = null;
            for(Integer s : students){
                if(prev != null){
                    int d = (s - prev) / 2;
                    if(d > dist){
                        dist = d;
                        student = prev + d;
                    }
                }
                prev = s;
            }
            if(n - 1 - students.last() > dist){
                student = n - 1;
            }
        }
        students.add(student);
        return student;
    }
    
    public void leave(int p) {
        students.remove(p);
        return;
    }
}
/**
 * Your ExamRoom object will be instantiated and called as such:
 * ExamRoom obj = new ExamRoom(n);
 * int param_1 = obj.seat();
 * obj.leave(p);
 */
```
## [670. Maximum Swap](https://leetcode.com/problems/maximum-swap/)
```java
class Solution {
    public int maximumSwap(int num) {
        char[] array = Integer.toString(num).toCharArray();
        int[] cnt = new int[10];
        for(int i = 0; i < array.length; i++){
            cnt[array[i] - '0'] = i;
        }
        
        for(int i = 0; i < array.length; i++){
            for(int j = 9; j > array[i] - '0'; j--){
                if(cnt[j] > i){
                    char tmp = array[i];
                    array[i] = array[cnt[j]];
                    array[cnt[j]] = tmp;
                    return Integer.valueOf(new String(array));
                }
            }
        }
        return num;
    }
}
```
- 先记录每位数字出现的最后index
- 然后两个for loop，第一个从左往右扫，内层for loop从9往0扫，从大到小，如果出现的数字index大于当前index，就swap

## [347. Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/)
```java
class Solution {
    int[] unique;
    Map<Integer, Integer> map = new HashMap<>();
    public int[] topKFrequent(int[] nums, int k) {
        for(int num : nums){
            map.put(num, map.getOrDefault(num, 0) + 1);
        }
        unique = new int[map.size()];
        int n = unique.length;
        int i = 0;
        for(int key : map.keySet()){
            unique[i++] = key;
        }
        quickSelect(0, n - 1, n - k);
        return Arrays.copyOfRange(unique, n - k, n);
        
        
    }
    private void quickSelect(int left, int right, int target){
        int cur = partition(left, right);
        if(cur == target){
            return;
        }else if(cur < target){
            quickSelect(cur + 1, right, target);
        }else{
            quickSelect(left, cur - 1, target);
        }
    }
    private int partition(int left, int right){
        int pivot = map.get(unique[right]);
        int wall = left;
        for(int i = left; i <= right; i++){
            if(map.get(unique[i]) < pivot){
                swap(unique, i, wall);
                wall++;
            }
        }
        swap(unique, wall, right);
        return wall;
        
    }
    private void swap(int[] unique, int i, int j){
        int tmp = unique[i];
        unique[i] = unique[j];
        unique[j] = tmp;
    }
}
```
- max heap， 存进去，然后poll前k个元素
  - tc: O(NlogN) sc: O(N)
- min heap，维持size在k
  - tc: O(NlogK) sc: O(K)
- quick select

## [215. Kth Largest Element in an Array](https://leetcode.com/problems/kth-largest-element-in-an-array/)
```java
class Solution {
    public int findKthLargest(int[] nums, int k) {
        int n = nums.length;
        int left = 0;
        int right = n - 1;
        int target = n - k;
        return quickSelect(left, right, target, nums);
    }
    private int quickSelect(int left, int right, int target, int[] nums){
        int pivot = partition(nums, left, right);
        if(pivot == target){
            return nums[pivot];
        }else if(pivot < target){
            return quickSelect(pivot + 1, right, target, nums);
        }else{
            return quickSelect(left, pivot - 1, target, nums);
        }
    }
    public int partition(int[] nums, int left, int right){
        int pivot = nums[left];
        int j = left;
        for(int i = left + 1; i <= right; i++){
            if(nums[i] < pivot){
                j++;
                swap(nums, j, i);
            }
        }
        swap(nums, left, j);
        return j;
    }
    public void swap(int[] nums, int i, int j){
        int tmp = nums[i];
        nums[i] = nums[j];
        nums[j] = tmp;
    }
}
```
- max heap， 存进去，然后poll前k个元素
  - tc: O(NlogN) sc: O(N)
- min heap，维持size在k
  - tc: O(NlogK) sc: O(K)
- quick select

## [394. Decode String](https://leetcode.com/problems/decode-string/)
```java
class Solution {
    public String decodeString(String s) {
        char[] sa = s.toCharArray();
        Deque<Integer> num = new ArrayDeque<>();
        Deque<StringBuilder> str = new ArrayDeque<>();
        StringBuilder sb = new StringBuilder();
        int carry = 0;
        for(char c : sa){
            if(c >= '0' && c <= '9'){
                carry = carry * 10 + (c - '0');
            }else if(c == '['){
                num.addLast(carry);
                str.addLast(sb);
                carry = 0;
                sb = new StringBuilder();
            }else if(c == ']'){
                StringBuilder sbTmp = str.removeLast();
                int n = num.removeLast();
                while(n > 0){
                    sbTmp.append(sb);
                    n--;
                }
                sb = sbTmp;
            }else{
                sb.append(c);
            }
        }
        return sb.toString();
    }
}
```
## [337. House Robber III](https://leetcode.com/problems/house-robber-iii/)
```java
class Solution {
    public int rob(TreeNode root) {
        int[] dp = help(root);
        return Math.max(dp[0], dp[1]);
    }
    private int[] help(TreeNode node){
        if(node == null){
            return new int[]{0, 0};
        }
        int[] dp = new int[2];
        int[] left = help(node.left);
        int[] right = help(node.right);
        dp[0] = Math.max(left[0], left[1]) + Math.max(right[0], right[1]);
        dp[1] = node.val + left[0] + right[0];
        return dp;
    }
}
```
- 二维数组记录，0代表不抢，1代表抢

## [993. Cousins in Binary Tree](https://leetcode.com/problems/cousins-in-binary-tree/)
```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    int xDepth = 0;
    int yDepth = 0;
    TreeNode xParent = null;
    TreeNode yParent = null;
    boolean xFind = false;
    boolean yFind = false;
    public boolean isCousins(TreeNode root, int x, int y) {
        help(root, null, 0, x, y);
        return yDepth == xDepth && xParent != yParent;
        
    }
    private void help(TreeNode node, TreeNode parent, int depth, int x, int y){
        if(node == null){
            return;
        }
        if(node.val == x){
            xDepth = depth;
            xFind = true;
            xParent = parent;
        }else if(node.val == y){
            yDepth = depth;
            yFind = true;
            yParent = parent;
        }
        if(xFind && yFind){
            return;
        }
        help(node.left, node, depth + 1, x, y);
        help(node.right, node, depth + 1, x, y);
    
    }
}
```