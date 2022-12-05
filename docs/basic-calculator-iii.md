---
id: basic-calculator-iii
title: Basic Calculator III
sidebar_label: Basic Calculator III
---
## Description
<div class="description">
null
</div>

## Solution(python3)
```python3
class Solution:
    def calculate(self, s: str) -> int:
        if len(s) == 0:
            return 0
        stack = []
        sign = '+'
        num = 0
        i = 0
        while i < len(s):
            c = s[i]
            if c.isdigit():
                num = num*10+int(c)

            if c == '(':
                # find the corresponding ")"
                pCnt = 0
                end = 0
                clone = s[i:]
                while end < len(clone):
                    if clone[end] == '(':
                        pCnt += 1
                    elif clone[end] == ')':
                        pCnt -= 1
                        if pCnt == 0:
                            break
                    end += 1
                # do recursion to calculate the sum within the next (...)
                num = self.calculate(s[i+1:i+end])
                i += end

            if i + 1 == len(s) or (c == '+' or c == '-' or c == '*' or c == '/'):
                if sign == '+':
                    stack.append(num)
                elif sign == '-':
                    stack.append(-num)
                elif sign == '*':
                    stack[-1] = stack[-1]*num
                elif sign == '/':
                    stack[-1] = int(stack[-1]/float(num))
                sign = c
                num = 0
            i += 1

        return sum(stack)   
```