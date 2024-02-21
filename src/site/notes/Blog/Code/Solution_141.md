---
{"aliases":"Solution_141","category":"leetcode","tags":["leetcode"],"status":"published","link":"NA","date created":"2023-03-10 Fri 07:42:32","date modified":"2024-02-21 Wed 19:14:47","dg-publish":true,"permalink":"/Blog/Code/Solution_141/","dgPassFrontmatter":true}
---


## 题

给你一个链表的头节点 head ，判断链表中是否有环。

如果链表中有某个节点，可以通过连续跟踪 next 指针再次到达，则链表中存在环。 为了表示给定链表中的环，评测系统内部使用整数 pos 来表示链表尾连接到链表中的位置（索引从 0 开始）。注意：pos 不作为参数进行传递 。仅仅是为了标识链表的实际情况。

如果链表中存在环 ，则返回 true 。 否则，返回 false 。

## 解

第一反应是使用双指针，快慢指针总会相遇。更进阶一点是要判断环发生的位置，加些计算逻辑也可得到。

```scala
object Solution141 {  
  def hasCycle(head: ListNode): Boolean = {  
    if (head == null || head.next == null) return false  
  
    var slow: ListNode = head  
    var fast: ListNode = head.next  
    while (slow != fast) {  
      if (fast == null || fast.next == null) return false  
  
      slow = slow.next  
      fast = fast.next.next  
    }  
    true  
  }  
}
```
