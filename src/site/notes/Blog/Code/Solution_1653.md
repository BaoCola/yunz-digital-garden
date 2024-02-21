---
{"aliases":"Solution_1653","category":"leetcode","tags":["leetcode","动态规划"],"status":"published","link":"NA","date created":"2023-03-06 Mon 07:57:19","date modified":"2024-02-21 Wed 19:13:16","dg-publish":true,"permalink":"/Blog/Code/Solution_1653/","dgPassFrontmatter":true}
---


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
