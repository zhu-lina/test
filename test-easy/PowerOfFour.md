## 问题分析：
#### 给一个整数，写一个函数来判断它是否为4的幂。
## 编程实现：
```c++
class Solution {
public:
    bool isPowerOfFour(int num) {
         if(num == 1) return true;
    if(num <= 0) return false;
    if(num & 0x03)  return false;
        else return isPowerOfFour(num / 4);
    }
};
```
## 总结体会：
#### 利用if语句先排除非零负整数，然后采用递归的思想依次对整数进行判断看是否为4的幂.
