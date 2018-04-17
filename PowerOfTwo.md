## 问题分析：

  给定一个整数，写一个函数来确定它是否是2的幂.
## 编程实现：
```c++
class Solution {
public:
    bool isPowerOfTwo(int n) {
          if (n == 0)
      return false;
    else if (n == 1)
      return true;
    else if (n%2==0)
         return isPowerOfTwo(n/2);
    else
       return false;
}
    };
```
## 总结体会：
 使用if-else语句对输入的n进行判断，采用递归思想，最终确定是否为2的幂.
