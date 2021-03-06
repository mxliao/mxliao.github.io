---
layout:     post
title:      "Problem: Number of Nodes in a Complete Tree"
date:       2015-02-18 00:00:00
author:     "Marcy"
header-img: "img/post-bg-2015.jpg"
catalog: true
category: algnote
algnote-tags:
    - Coding Interview
    - Coding Practice
    - Algorithms and Data Structures
    - Binary Search
    - Medium
---

## Question

Given a complete binary tree, count the number of nodes.

Definition of a complete binary tree from Wikipedia:
In a complete binary tree every level, except possibly the last, is completely filled, and all nodes in the last level are as far left as possible. It can have between 1 and 2h nodes inclusive at the last level h.

## Solution 1
TODO

#### Code
```java
class Solution {
    public int countNodes(TreeNode root) {
        TreeNode node = root;
        int count = 0;
        int leftHeight = getLeftHeight(node);
        while(node != null) {
            int l2 = getLeftHeight(node.right);
            if(leftHeight == l2+1) {
                node = node.right;
            }
            else {
                node = node.left;
            }
            count += 1 << l2;
            leftHeight --;
        }
        
        return count;
    }
    
    public int getLeftHeight(TreeNode root) {
        int h = 0;
        TreeNode node = root;
        while(node != null) {
            h++;
            node = node.left;
        }
        
        return h;
    }
}
```

#### Performance
TODO

## Solution 2
TODO

#### Code
```java
class Solution {
    public int countNodes(TreeNode root) {
        return countNodes(root, getHeight(root));
    }
    
    public int countNodes(TreeNode root, int height) {
        if(root == null) return 0;
        int count = 1;
        
        int rightChildHeight = getHeight(root.right);
        int leftChildHeight = height - 1;

        if(leftChildHeight == rightChildHeight) {
            count += Math.pow(2,leftChildHeight)-1;
            count += countNodes(root.right, rightChildHeight);
        }
        else {
            count += Math.pow(2,rightChildHeight) - 1;
            count += countNodes(root.left, leftChildHeight);
        }
        
        return count;
        
    }
    
    private int getHeight(TreeNode node) {
        int height = 0;
        while(node != null) {
            node = node.left;
            height ++;
        }
        
        return height;
    }
}
```

#### Performance
TODO
