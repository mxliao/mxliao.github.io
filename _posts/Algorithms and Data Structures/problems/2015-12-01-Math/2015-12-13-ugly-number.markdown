---
layout:     post
title:      "Problem: Ugly Number"
date:       2015-02-18 00:00:00
author:     "Marcy"
header-img: "img/post-bg-2015.jpg"
catalog: true
category: algnote
algnote-tags:
    - Coding Interview
    - Coding Practice
    - Algorithms and Data Structures
    - Math
    - Easy
---

## Question

Write a program to check whether a given number is an ugly number.

Ugly numbers are positive numbers whose prime factors only include 2, 3, 5. For example, 6, 8 are ugly while 14 is not ugly since it includes another prime factor 7.

**Note:**
- 1 is typically treated as an ugly number.
- Input is within the 32-bit signed integer range.

## Solution
TODO

#### Code
```java
class Solution {
    public boolean isUgly(int num) {
        if(num <= 0) return false;
        if(num == 1) return true;
        while(num != 1) {
            if(num % 2 == 0) num/=2;
            else if(num % 3 == 0) num /=3;
            else if(num % 5 == 0) num /=5;
            else return false;
        }

        return true;
    }
}
```

## Performance
TODO
