---
id: design-phone-directory
title: Design Phone Directory
sidebar_label: Design Phone Directory
---
## Description
<div class="description">
null
</div>

## Solution(python)
```python
class PhoneDirectory(object):

    def __init__(self, maxNumbers):
        self.__curr = 0
        self.__numbers = range(maxNumbers)
        self.__used = [False] * maxNumbers


    def get(self):
        if self.__curr == len(self.__numbers):
            return -1
        number = self.__numbers[self.__curr]
        self.__curr += 1
        self.__used[number] = True
        return number
        

    def check(self, number):
        return 0 <= number < len(self.__numbers) and \
               not self.__used[number]
        

    def release(self, number):
        if not 0 <= number < len(self.__numbers) or \
           not self.__used[number]:
            return
        self.__used[number] = False
        self.__curr -= 1
        self.__numbers[self.__curr] = number
        


# Your PhoneDirectory object will be instantiated and called as such:
# obj = PhoneDirectory(maxNumbers)
# param_1 = obj.get()
# param_2 = obj.check(number)
# obj.release(number)
```