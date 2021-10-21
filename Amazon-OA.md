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