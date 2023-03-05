---
{"aliases":"solution_1487","category":"leetcode","tags":["leetcode"],"status":"publish","link":"NA","date created":"2023-03-03 Fri 07:24:47","date modified":"2023-03-06 Mon 07:30:13","dg-publish":true,"permalink":"/02.Blog/leetcode/solution_1487/","dgPassFrontmatter":true}
---


<< [[leetcode\|leetcode]] | [[03.Diary/2023-03-03_Fri\|2023-03-03_Fri]]

> What we think determines what happens to us, so if we want to change our lives, we need to stretch our minds.  
> — <cite>Wayne Dyer</cite>

![photo by Stefan Kunze on Unsplash](https://images.unsplash.com/photo-1437652633673-cc02b9c67a1b?crop=entropy&cs=tinysrgb&fm=jpg&ixid=MnwzNjM5Nzd8MHwxfHJhbmRvbXx8fHx8fHx8fDE2Nzc3OTk0OTQ&ixlib=rb-4.0.3&q=80&w=200&h=200)

## 题

[link](https://leetcode.cn/problems/making-file-names-unique/)

给你一个长度为 n 的字符串数组 names 。你将会在文件系统中创建 n 个文件夹：在第 i 分钟，新建名为 names[i] 的文件夹。

由于两个文件 不能 共享相同的文件名，因此如果新建文件夹使用的文件名已经被占用，系统会以 (k) 的形式为新文件夹的文件名添加后缀，其中 k 是能保证文件名唯一的 最小正整数 。

返回长度为 n 的字符串数组，其中 ans[i] 是创建第 i 个文件夹时系统分配给该文件夹的实际名称。

## 解

- 数据结构

使用一个 LinkedHashSet 来存文件名，避免重复，保证有序。

- 逻辑

1. 如果文件名不在 set 中，直接添加；
2. 如果文件名在 set 中，找不存在的最小后缀文件名，从 1 开始累加；

```java
import scala.collection.mutable  
  
object Solution1487 {  
  def getFolderNames(names: Array[String]): Array[String] = {  
    val set = new mutable.LinkedHashSet[String]()  
    names.foreach(n => {  
      if (set.contains(n)) {  
        var minIndex = 1  
        while (set.contains(s"$n($minIndex)")) {  
          minIndex += 1  
        }  
        set.add(s"$n($minIndex)")  
      } else {  
        set.add(n)  
      }  
    })  
    set.toArray  
  }  
}
```
