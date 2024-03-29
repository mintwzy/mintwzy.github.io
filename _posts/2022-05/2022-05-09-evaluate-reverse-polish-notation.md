---
title: '[LeetCode 150] Evaluate Reverse Polish Notation'
published: true
tags: Stack
---

## Problem

Evaluate the value of an arithmetic expression in Reverse Polish Notation.

Valid operators are `+`, `-`, `*`, and `/`. Each operand may be an integer or
another expression.

**Note** that division between two integers should truncate toward zero.

It is guaranteed that the given RPN expression is always valid. That means the
expression would always evaluate to a result, and there will not be any
division by zero operation.

## Example 1:

```
Input: tokens = ["2","1","+","3","*"]
Output: 9
Explanation: ((2 + 1) * 3) = 9
```

## Example 2:

```
Input: tokens = ["4","13","5","/","+"]
Output: 6
Explanation: (4 + (13 / 5)) = 6
```

## Example 3:

```
Input: tokens = ["10","6","9","3","+","-11","*","/","*","17","+","5","+"]
Output: 22
Explanation: ((10 * (6 / ((9 + 3) * -11))) + 17) + 5
= ((10 * (6 / (12 * -11))) + 17) + 5
= ((10 * (6 / -132)) + 17) + 5
= ((10 * 0) + 17) + 5
= (0 + 17) + 5
= 17 + 5
= 22
```
 
### Constraints:

- `1 <= tokens.length <= 104`
- `tokens[i]` is either an operator: `"+"`, `"-"`, `"*"`, or `"/"`, or an integer in the range `[-200, 200]`.

## Thoughts

- Try with stack?

## Typescript

```typescript
function evalRPN(tokens: string[]): number {
    const stack: number[] = [];
    
    for(let c of tokens){
        if(c === '+') {
            stack.push(stack.pop() + stack.pop())
        } else if(c === '-'){
            const num1: number = stack.pop()
            const num2: number = stack.pop();
            stack.push(num2 - num1)
        } else if(c === '*'){
            stack.push(stack.pop() * stack.pop())
        } else if(c === '/'){
            const num1: number = stack.pop()
            const num2: number = stack.pop();
            const temp: number = num2/num1;
            stack.push(temp > 0 ? Math.floor(temp) : Math.ceil(temp))
        } else {
            stack.push(parseInt(c))
        }
    }
    
    return stack[0]
};
```

## Reference

- [https://leetcode.com/problems/evaluate-reverse-polish-notation/](https://leetcode.com/problems/evaluate-reverse-polish-notation/)