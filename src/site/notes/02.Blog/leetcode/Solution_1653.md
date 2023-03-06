---
{"aliases":"Solution_1653","category":"leetcode","tags":["leetcode, 动态规划"],"status":"publish","link":"NA","date created":"2023-03-06 Mon 07:57:19","date modified":"2023-03-06 Mon 08:02:27","dg-publish":true,"permalink":"/02.Blog/leetcode/Solution_1653/","dgPassFrontmatter":true}
---


<< [[leetcode\|leetcode]] | [[2023-03-06_Mon\|2023-03-06_Mon]]

> The most successful people are those who are good at plan B.  
> — <cite>James A. Yorke</cite>

![photo by Redd F on Unsplash](https://images.unsplash.com/photo-1493589976221-c2357c31ad77?crop=entropy&cs=tinysrgb&fm=jpg&ixid=MnwzNjM5Nzd8MHwxfHJhbmRvbXx8fHx8fHx8fDE2NzgwNjA2NDg&ixlib=rb-4.0.3&q=80&w=200&h=200)

## 题

给你一个字符串 s ，它仅包含字符 'a' 和 'b'​​​​ 。

你可以删除 s 中任意数目的字符，使得 s 平衡 。当不存在下标对 (i,j) 满足 i < j ，且 s[i] = 'b' 的同时 s[j]= 'a' ，此时认为 s 是 平衡 的。

请你返回使 s 平衡 的 最少 删除次数。

## 解

从字符串最后往前：
- 如果字符为 b，则问题规模缩小 1；
- 如果字符为 a，则有两个选择，取较小值；
	- 删除前面所有的 b；
	- 删除此 b，问题规模再缩小 1，但结果需要加 1。

```scala
object Solution1653 {  
  def minimumDeletions(s: String): Int = {  
    var f = 0  
    var cntB = 0  
    s.toArray.foreach(c => {  
      if (c == 'b') {  
        cntB += 1  
      } else {  
        f = Math.min(f + 1, cntB)  
      }  
    })  
    f  
  }  
}
```
