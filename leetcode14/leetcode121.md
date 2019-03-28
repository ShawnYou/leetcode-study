### 121-买卖股票的最佳时机I

[leetcode地址](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock/solution/)

解法一

###暴力法

关键： 找到数组中的最大差值， max(arr[j]-arr[i]), 其中j>i

采用暴力法遍历，直到取到最大的利润

时间复杂度：O(n^2)

空间复杂度：O(1)

```
class Solution {
    public int maxProfit(int[] prices) {
        int maxProfit = 0;
        for(int i = 0;i<prices.length;i++){
            for(int j = i+1;j<prices.length;j++){
                int profit = prices[j] - prices[i];
                if(profit > maxProfit){
                    maxProfit = profit;
                }
            }
        }
        return maxProfit;
    }
}
```

### 一次遍历

思路: 只关心最小的价格和最大的收益

时间复杂度: 只遍历了一次，所以时间复杂度为O(n)

空间复杂度: O(1)
```
class Solution {
    public int maxProfit(int[] prices) {
        int minPrice = Integer.MAX_VALUE;
        int maxProfit = 0;
        for(int i = 0;i<prices.length;i++){
            if(prices[i]<minPrice){
                minPrice = prices[i];
            }else if(prices[i]-minPrice>maxProfit){
                maxProfit = prices[i] - minPrice;
            }
        }
        return maxProfit;
    }
}
```