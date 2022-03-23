# Coinbase Interview
## Phone Screen
### Buy and Sell books
![](https://markpersonal.oss-us-east-1.aliyuncs.com/pic/20220216215038.png)

Follow up: 实现会expire的 order，比如说buyer 的一个order valid for 10 min，然后自动expire


构建两个堆，一个“最小堆”记录sell, 一个“最大堆”记录buy. 每次遇到BUY或者SELL都可以直接判断并更新状态；
follow up: 面试官要考察堆内部的元素记录生命周期，这个问题非常类似于蠡口司巴铃，就是加上一个timestamp，在每次判断是否撮合交易时，使用延迟修改技术将不符合条件的order从堆中删掉；

- 输入输出的类型
- method具体实现（buy & sell， anything else?）
- 使用class封装
  - 开始直接封装
  - 还是follow up的时候封装
  - 封装的时候要不要用getter and setter
- try catch？
- 打印输出吗？
- priorityQueue的位置
- follow up 什么时候maintain heap
- test case

marketPlace
pq<deal>

deal
int price
boolean isSell
long expired time = curtime + expiredTime

main 创建 marketplace


Mock:

1. Clarify the meaning of the problem:

2. buy collection, sell collection, to store the offer price;
for somebody offer to sell, Tim offers to sell at $150, the other side's buy offer price should >= 150 that would make a deal, under meeting this requirment, the higher price, the better, so we just need to find the highest price in the buy collection:
    1. traverse O(N)
    2. sort O(NlogN)
    3. PQ O(logN)

3. use test Case to dry run:
4. input check, any negative number as price?
5. 

## VO
### Currency Exchange

给一个list的Currency exchange rate，双向的，比如 USD -> CAD : 1.3, CAD -> USD: 0.72, BTC -> USD: 1000, USD -> BTC: 1/999。写一个Currency exchange method 来求出从 currency A 到currency B的最大值。



时间是n!，n是货币种类，空间是n + e，e是edge数量

- 路径最长 还是 最大值
- 


### Connnect 4