---
{"aliases":"Solution121_买卖股票的最佳时机","category":"leetcode","tags":["leetcode"],"status":"publish","link":"NA","date created":"2023-03-10 Fri 07:22:49","date modified":"2023-03-10 Fri 07:22:49","dg-publish":true,"permalink":"/02.Blog/leetcode/Solution121_买卖股票的最佳时机/","dgPassFrontmatter":true}
---


<< [[leetcode\|leetcode]] | [[2023-03-10_Fri\|2023-03-10_Fri]]

## 题

给定一个数组 prices ，它的第 i 个元素 prices[i] 表示一支给定股票第 i 天的价格。

你只能选择 某一天 买入这只股票，并选择在 未来的某一个不同的日子 卖出该股票。设计一个算法来计算你所能获取的最大利润。

返回你可以从这笔交易中获取的最大利润。如果你不能获取任何利润，返回 0 。

## 解

一次遍历，记录当前值与其之前最小值的差值，取最大返回。

```scala
object Solution121 {  
  def maxProfit(prices: Array[Int]): Int = {  
    var max = 0  
    var min = Int.MaxValue  
    prices.foreach(p => {  
      if (p < min) min = p  
      max = Math.max(max, p - min)  
    })  
    max  
  }  
}
```