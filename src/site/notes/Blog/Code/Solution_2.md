---
{"aliases":"Solution_2","category":"leetcode","tags":["leetcode"],"status":"published","link":"NA","date created":"2023-03-08 Wed 07:20:20","date modified":"2024-02-21 Wed 19:11:05","dg-publish":true,"permalink":"/Blog/Code/Solution_2/","dgPassFrontmatter":true}
---


## 题

给你两个 非空 的链表，表示两个非负的整数。它们每位数字都是按照 逆序 的方式存储的，并且每个节点只能存储 一位 数字。

请你将两个数相加，并以相同形式返回一个表示和的链表。

你可以假设除了数字 0 之外，这两个数都不会以 0 开头。

![Pasted image 20230308072141](https://github.com/Yunz93/PicRepo/raw/main/image/202303080738418.png)

## 解

此题降低了难度，使用链表逆向存储数字，操作会更简单。

解题的关键点在于进位的处理：
- 初始进位为 0；
- 进位与两数当前位的数字相加，确定下一位的进位与本位的数值；
- 如果当前位仅存在一个数有值，则只取该数。

```scala
class ListNode(_x: Int = 0, _next: ListNode = null) {  
  var next: ListNode = _next  
  var x: Int = _x  
}  
  
object Solution2 {  
  def addTwoNumbers(l1: ListNode, l2: ListNode): ListNode = (l1, l2) match {  
    case (l1, null) => l1  
    case (null, l2) => l2  
    case (_, _) =>  
      val d = (l1.x + l2.x) / 10  
      val r = (l1.x + l2.x) % 10  
      val ln = new ListNode(r)  
  
      val next = if (d > 0)  
        addTwoNumbers(new ListNode(1), addTwoNumbers(l1.next, l2.next))  
      else  
        addTwoNumbers(l1.next, l2.next)  
  
      ln.next = next  
      ln  
  }  
}
```
