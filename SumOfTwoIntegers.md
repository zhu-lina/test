## 问题分析：
####计算两个整数a和b的和,但不允许使用运算符+和-.
## 编程实现：
```c++
class Solution {
public:
    int getSum(int a, int b) {
     while(b!=0)
     {
         int c=a&b;
         a=a^b;
         b=c<<1;
     }
        return a;
    }
};
```
## 总结体会：
####给定两个数字a和b,a&b返回由a和b上的'1'位组成的数字。当它左移一位时，产生进位。
