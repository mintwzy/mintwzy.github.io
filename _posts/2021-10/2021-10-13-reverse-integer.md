---
title: "[LeetCode 7] Reverse Integer"
published: true
tags: String
---

## Problem

Given a signed 32-bit integer x, return x with its digits reversed. If reversing
x causes the value to go outside the signed 32-bit integer range [-231, 231 -
1], then return 0.

Assume the environment does not allow you to store 64-bit integers (signed or unsigned).

### Example 1:

```
Input: x = 123
Output: 321
```

### Example 2:

```
Input: x = -123
Output: -321
```

### Example 3:

```
Input: x = 120
Output: 21
```

### Example 4:

```
Input: x = 0
Output: 0
```
 
### Constraints:

- `-2^31 <= x <= 2^31 - 1`

## Thoughts

- we do string manipulation

## Code

```typescript
function reverse(x: number): number {
    const sign = x < 0 ? -1 : 1;
    const temp = parseInt(x.toString().split("").reverse().join(""));
    return temp > 0x7FFFFFFF ? 0 : sign * temp
};
```

## Reference

- [https://leetcode.com/problems/reverse-integer/](https://leetcode.com/problems/reverse-integer/)