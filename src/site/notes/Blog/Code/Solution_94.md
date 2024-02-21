---
{"aliases":"Solution_94","category":"leetcode","tags":["leetcode"],"status":"published","link":"NA","date created":"2023-03-09 Thu 07:40:15","date modified":"2024-02-21 Wed 19:13:48","dg-publish":true,"permalink":"/Blog/Code/Solution_94/","dgPassFrontmatter":true}
---


## 题

给定一个二叉树的根节点 `root` ，返回 _它的 **中序** 遍历_ 。

**示例 1：**

![](https://assets.leetcode.com/uploads/2020/09/15/inorder_1.jpg)

输入：root = [1,null,2,3]  
输出：[1,3,2]

## 解

中序遍历。

```scala
object Solution94 {  
  def inorderTraversal(root: TreeNode): List[Int] = {  
    Option(root).map(n => inorderTraversal(n.left) ::: List(n.value) ::: inorderTraversal(n.right)).getOrElse(List())  
  }  
}
```
