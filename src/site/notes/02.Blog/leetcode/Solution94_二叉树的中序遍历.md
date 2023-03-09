---
{"aliases":"Solution94_二叉树的中序遍历","category":"leetcode","tags":["leetcode"],"status":"publish","link":"NA","date created":"2023-03-09 Thu 07:40:15","date modified":"2023-03-09 Thu 08:00:25","dg-publish":true,"permalink":"/02.Blog/leetcode/Solution94_二叉树的中序遍历/","dgPassFrontmatter":true}
---


<< [[leetcode\|leetcode]] | [[2023-03-09_Thu\|2023-03-09_Thu]]

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
