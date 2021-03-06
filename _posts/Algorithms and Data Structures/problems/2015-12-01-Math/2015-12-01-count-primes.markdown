---
layout:     post
title:      "Problem: Count Primes"
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
    - Medium
---

## Question

Count the number of prime numbers less than a non-negative number, n.

## Solution
TODO

#### Code
```java
class Solution {
    public int countPrimes(int n) {
        if(n<=2) return 0;
        List<Integer> primes = new ArrayList();
        primes.add(2);
        for(int i=3; i<=n-1; i+=2) {
            boolean found = false;
            for(int prime : primes) {
                if(i % prime == 0) {
                    found = true;
                    break;
                }
            }
            if(!found) primes.add(i);
        }

        return primes.size();
    }
}
```

```java
// The Sieve Of Eratosthenes
class Solution {
    public int countPrimes(int n) {
        boolean[] isNotPrimes = new boolean[n];
        int count = 0;
        for(int i=2; i<n; i++) {
            if(!isNotPrimes[i]) {
                count++;
                for(int j=2; i*j<n; j++) {
                    isNotPrimes[i*j] = true;
                }
            }
        }
        return count;
    }
}
```

## Performance
TODO
