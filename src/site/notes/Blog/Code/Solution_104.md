---
{"aliases":"Solution_104","category":"leetcode","tags":["leetcode"],"status":"published","link":"NA","date created":"2023-03-09 Thu 07:33:57","date modified":"2024-02-21 Wed 19:11:13","dg-publish":true,"permalink":"/Blog/Code/Solution_104/","dgPassFrontmatter":true}
---


## 题

给定一个二叉树，找出其最大深度。

二叉树的深度为根节点到最远叶子节点的最长路径上的节点数。

**说明:** 叶子节点是指没有子节点的节点。

示例：  
给定二叉树 [3,9,20,null,null,15,7]，

```shell
    3
   / \
  9  20
    /  \
   15   7
```

返回它的最大深度 3 。

## 解

最简单的二叉树，递归求解。

```scala
class TreeNode(_value: Int = 0, _left: TreeNode = null, _right: TreeNode = null) {  
  var value: Int = _value  
  var left: TreeNode = _left  
  var right: TreeNode = _right  
}  
  
object Solution104 {  
  def maxDepth(root: TreeNode): Int = {  
    if (root == null) {  
      return 0  
    }  
  
    Math.max(maxDepth(root.left), maxDepth(root.right)) + 1  
  }  
}
```
